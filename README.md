# Crack Recon

`crack_recon` is a project for processing scans of samples to detect cracks or vessel-like structures. The processing explores multiple pipelines, including single-channel and multi-channel fusion, to generate binary masks from different types of scans.

> **Note:** The deterministic pipeline was developed through trial-and-error. A plan to replace it with a small ML model exists, but the model is not yet implemented as the dataset is still being collected.

---

## Project Structure

```
crack_recon/
├─ output_samples/       # Processed outputs from the pipelines
└─ crack_recon.ipynb     # Main Jupyter notebook with all code
```
 
- **output_samples/** – Contains processed versions of the samples generated using the pipelines in `crack_recon.ipynb`.  
- **crack_recon.ipynb** – The entire processing workflow:  
  - Channel-specific pipelines for blue, green, and transmission scans  
  - Multi-channel fusion  
  - Binary mask generation and morphological cleaning
* The raw input images are too big for this repo and do not belong to me. 

---

## Features

- **Channel-specific pipelines**  
  - Blue channel: main detector  
  - Green channel: supportive, highlights thicker structures  
  - Transmission channel: conservative, used for validation  

- **Multi-channel fusion**  
  - Combines vesselness maps from all three channels  
  - Blue dominates detection, green and transmission refine confidence  

- **Binary mask generation**  
  - Contrast enhancement with CLAHE  
  - Sato filter for vesselness detection  
  - Morphological cleaning for noise reduction  
  - Outputs boolean masks

---

## Future Work

- **ML-based detection**  
  - The current deterministic pipeline has limitations.  
  - A small ML model is planned to improve detection using multi-channel data.  
  - ML training will begin once sufficient annotated data is collected.

---



---

## License

[MIT License] (if applicable)

