# Session 3: Teaching Machines to See and Click - Model Finetuning

## 🎯 What We Covered

In Session 3 the focus shifted to **models** for GUI agents, exploring their architectures, fine-tuning strategies, and practical challenges. This session provided an in-depth look at implementing and customizing these models to work effectively with GUI data.

### Key Highlights:

*   The session primarily focused on **models** for GUI agents, including a discussion of various **architectures** and **fine-tuning strategies**.

*   Several specific GUI agent models were examined, including **OS Atlas**, **MiMo-VL**, **ShowUI-2B**, and **GUI-Actor**.

*   A recurring theme was the **critical role of Quinn VL** (Quinn 2VL, Quinn 2.5VL) as a foundational backbone for GUI agents, largely due to its support for arbitrary image resolutions, unique embedding techniques, and its open-source nature.

*   Common **pain points** encountered when working with these models were discussed, such as **output standardization inconsistencies** (e.g., coordinates, bounding boxes, natural language), **extreme sensitivity to prompt formatting** (like whitespace or word order), and the challenges of **multi-target detection**.

*   The session highlighted a lack of **built-in explainability features** in many models and their consistent struggle with **small text and OCR** on high-resolution GUI screenshots.

*   Attendees learned a **detailed methodology for customizing GUI-Actor** for specific domains, which involved several key steps:

    *   **Formatting the dataset**: This included building a transformation layer between FiftyOne's annotation system and GUI-Actor's expected format, converting coordinate systems (e.g., from `[x, y, width, height]` to `[x_min, y_min, x_max, y_max]`), and creating a **flattening mechanism** to transform single screenshots with multiple annotations into separate training examples to manage GPU memory. Interactions were structured as a **three-message conversation** (system prompt, user query with image, assistant response with action details).

    *   **Collating the dataset**: A specialized collator was implemented to transform structured message payloads into vision-language model inputs with **coordinate grounding**. This involved replacing coordinate text with special pointer tokens and developing a spatial reasoning system to map normalized coordinates to discrete visual token positions. **Multi-patch labeling** for bounding boxes was also implemented to create binary masks indicating visual token overlap with target regions

## 📚 Deep Dive Resources

### 👨🏽‍💻 **Code for this Session**

* [Dataset for training](https://huggingface.co/datasets/harpreetsahota/FiftyOne-GUI-Grounding-Train-with-Synthetic)

* [Benchmark dataset](https://huggingface.co/datasets/harpreetsahota/FiftyOne-GUI-Grounding-Eval)

* [Repo for fine-tuning GUI-Actor 3B model](https://github.com/harpreetsahota204/GUI-Actor-for-FiftyOne)

* [Testing GUI-Actor 3B on our benchmark dataset](https://github.com/harpreetsahota204/visual_agents_workshop/blob/main/session_3/Testing_GUI_Actor_3B_on_FiftyOne_App_Dataset.ipynb)

* [Fine-tuning notebook](https://github.com/harpreetsahota204/visual_agents_workshop/blob/main/session_3/Fine_tuning_GUI_Actor_3B_on_FiftyOne_App_Dataset_.ipynb)

### 🎥 **Watch the Session**

[![YouTube](https://img.shields.io/badge/YouTube-Watch%20Session-red?logo=youtube&logoColor=white)](https://www.youtube.com/watch?v=Lzl-ktGbAz8) [![Views](https://img.shields.io/youtube/views/d-bLgV3GFqE?style=social)](https://www.youtube.com/watch?v=Lzl-ktGbAz8)


### 📊 **Session Slides**

[![Google Slides](https://img.shields.io/badge/Google%20Slides-View%20Presentation-blue?logo=google&logoColor=white)](https://docs.google.com/presentation/d/1qF6BEevIyYLWENLAxh8dCJFw4uRfe54MvCc-xh8Rkwc/edit?usp=sharing)