# Session 2: From Pixels to Predictions, Building a GUI Dataset

## 🎯 What We Covered

In Session 2, titled "From Pixels to Predictions - Building GUI Datasets," the focus shifted from a historical perspective to the practical aspects of **building robust GUI Agent datasets**. This session provided an in-depth look at the diverse nature of GUI data and the methods for creating comprehensive and resilient datasets for training GUI agents.

### Key Highlights:

*   **Understanding GUI Agent Datasets**: The session explored the **many shapes of GUI data** and various GUI Agent datasets, including RICO, GUI-Odyssey, GUIAct, Mind2Web (multimodal), ShowUI (Desktop), ScreenSpot-Pro, ScreenSpot-v2, GroundUI, and Aria-UI. These datasets often contain rich element metadata, coordinate systems (like absolute desktop pixels with variable resolution), and actions.

*   **Observed Patterns and Challenges**: Discussions covered common patterns found in these datasets and the **challenges** they present. A significant challenge highlighted was **training pipeline complexity**, requiring dataset-specific coordinate conversion functions, multiple normalization steps (string parsing to pixel conversion to normalization), and robust edge case handling for issues like out-of-bounds or negative coordinates.

*   **Standardized Format: COCO4GUI**: The importance of a **standardized format** was addressed with the introduction of the **COCO4GUI format**, a COCO-based GUI dataset collector. Resources were provided for building datasets in this format and for a COCO4GUI FiftyOne dataset importer.

*   **Generating Synthetic Data for Robustness**: A key aspect of building robust datasets is **generating synthetic data**. This includes techniques such as:

    *   **Color inversion**: Simulates dark mode interfaces, covers OS-level contrast settings, and tests element detection in inverted color schemes, common in modern applications.

    *   **Colorblindness simulation**: Covers three types (Deuteranopia, Protanopia, Tritanopia) to ensure color-independent element detection and aligns with accessibility requirements.

    *   **Grayscale conversion**: Removes color as a primary feature, emphasizes structural patterns, simulates monochrome displays, and improves robustness to theme changes.

    *   **Task description augmentation with LLMs**: Handles different phrasings of the same task, maintains semantic meaning, and prepares for varied user instructions.

    *   A **Synthetic GUI samples plugin for FiftyOne** was also presented to facilitate this process.

## 📚 Deep Dive Resources

### 👨🏽‍💻 **Code for this Session**

The notebook used for this session can be found [here](https://github.com/harpreetsahota204/visual_agents_workshop/blob/main/session_2/working_with_gui_datasets.ipynb).

*   The tool used to create the dataset is **COCO4GUI - A COCO-based GUI dataset collector**. This tool is involved in building datasets in the **COCO4GUI format**. You can find it at: https://github.com/harpreetsahota204/gui_dataset_creator

*   The importer for loading datasets into the FiftyOne format is the **COCO4GUI FiftyOne dataset importer**. You can find it at: https://github.com/harpreetsahota204/coco4gui_fiftyone

*   The plugin for generating synthetic samples, which is part of the process for **generating synthetic data**, is the **Synthetic GUI samples plugin for FiftyOne**. You can find it at: https://github.com/harpreetsahota204/synthetic_gui_samples_plugins


### 🎥 **Watch the Session**

[![YouTube](https://img.shields.io/badge/YouTube-Watch%20Session-red?logo=youtube&logoColor=white)](https://www.youtube.com/watch?v=mCBJHQ5SYJg) [![Views](https://www.youtube.com/watch?v=mCBJHQ5SYJg?style=social)](https://www.youtube.com/watch?v=mCBJHQ5SYJg)


### 📊 **Session Slides**

[![Google Slides](https://img.shields.io/badge/Google%20Slides-View%20Presentation-blue?logo=google&logoColor=white)](https://docs.google.com/presentation/d/1KIrjqpvQ9bNa0Dv_wN3UetStCijn9Uf5rf1xjh6gJZA/edit?usp=sharing)