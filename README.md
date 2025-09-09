DICOM 3D Viewer 🏥
Show Image
<img width="1907" height="1077" alt="Image" src="https://github.com/user-attachments/assets/3ed42b05-2bcc-4632-b380-3626fb7be3ac" />
<img width="1907" height="1077" alt="Image" src="https://github.com/user-attachments/assets/3ed42b05-2bcc-4632-b380-3626fb7be3ac" />

A professional DICOM 3D visualization and analysis tool built with Python, VTK, and PyQt5. Designed for medical professionals, researchers, and students to visualize, analyze, and manipulate medical imaging data with precision and ease.

🎯 Overview
DICOM 3D Viewer provides comprehensive tools for loading, visualizing, and analyzing DICOM (Digital Imaging and Communications in Medicine) files. Whether you're working with CT scans, MRI images, or other medical imaging modalities, this tool offers intuitive 3D rendering and analysis capabilities.

✨ Features
📂 DICOM Support
Multi-format Loading: Support for single DICOM files and complete series
DICOM Directory Import: Load entire patient studies with automatic series detection
Metadata Display: Complete DICOM tag information and patient data
Series Management: Organize and switch between multiple image series
🎨 3D Visualization
Volume Rendering: High-quality 3D volume visualization
Multi-planar Reconstruction (MPR): Axial, Sagittal, and Coronal views
Surface Rendering: Isosurface extraction and mesh generation
Maximum Intensity Projection (MIP): Enhanced vessel and structure visualization
Interactive Rendering: Real-time manipulation with mouse and keyboard
🔧 Analysis Tools
Window/Level Adjustment: Precise contrast and brightness control
Measurement Tools: Distance, area, and volume measurements
Region of Interest (ROI): Draw and analyze specific regions
Histogram Analysis: Intensity distribution analysis
Cross-sectional Views: Synchronized multi-planar viewing
🖼️ Display Features
Zoom & Pan: Smooth navigation through images
Annotations: Add text and graphical annotations
Cine Mode: Animate through image stacks
Full-screen Mode: Distraction-free viewing
Multi-monitor Support: Extend workspace across displays
💾 Export Capabilities
Image Export: Save views as PNG, JPEG, TIFF
3D Model Export: STL, OBJ, PLY formats for 3D printing
Screenshot Tools: Capture current views and annotations
Report Generation: Generate analysis reports with measurements
🚀 Installation
Prerequisites
Python 3.8 or higher
OpenGL compatible graphics card (recommended)
Minimum 4GB RAM (8GB+ recommended for large datasets)
Quick Install
bash
# Clone the repository
git clone https://github.com/sohaila-emad/Dicom3D-Viewer.git
cd Dicom3D-Viewer

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Launch application
python main.py
Alternative Installation
bash
# Install via pip (if published)
pip install dicom3d-viewer

# Run from command line
dicom3d-viewer
📦 Dependencies
vtk>=9.0.0
PyQt5>=5.15.0
pydicom>=2.3.0
numpy>=1.20.0
matplotlib>=3.5.0
SimpleITK>=2.1.0
nibabel>=3.2.0
scipy>=1.7.0
Pillow>=8.0.0
🖥️ Screenshots
Main Interface
Show Image
Main application interface showing 3D volume rendering and control panels

Multi-planar Views
Show Image
Synchronized axial, sagittal, and coronal views with crosshair navigation

Volume Rendering
Show Image
High-quality 3D volume rendering with transfer function control

Measurement Tools
Show Image
Distance, area, and volume measurement tools in action

DICOM Metadata
Show Image
Comprehensive DICOM tag display and patient information

📖 Quick Start Guide
Loading DICOM Files
Single File
Click File → Open DICOM File or press Ctrl+O
Select a DICOM file from your system
The image will load in the main viewing area
DICOM Series
Click File → Open DICOM Directory or press Ctrl+D
Select a folder containing DICOM files
Choose from detected series in the dialog
Multiple series will be organized in the series panel
Basic Navigation
Rotate: Left mouse button + drag
Zoom: Mouse wheel or right mouse button + drag
Pan: Middle mouse button + drag
Window/Level: Ctrl + mouse drag
3D Rendering Controls
Use the Rendering panel to switch between:
Volume Rendering
Surface Rendering
Maximum Intensity Projection
Adjust Transfer Function for optimal visualization
Modify Opacity and Color settings
Making Measurements
Select measurement tool from toolbar
Click points on the image to define measurements
Results appear in the Measurements panel
Export measurements to CSV or include in reports
🔧 Advanced Features
Transfer Function Editing
python
# Custom transfer function example
viewer.set_transfer_function(
    opacity_points=[(0, 0.0), (500, 0.1), (1000, 0.8)],
    color_points=[(0, [0,0,0]), (500, [1,0.5,0]), (1000, [1,1,1])]
)
Batch Processing
python
# Process multiple DICOM series
from dicom3d_viewer import BatchProcessor

processor = BatchProcessor()
processor.add_directory("/path/to/dicom/studies")
processor.apply_processing_pipeline([
    "denoise",
    "normalize",
    "segment_organs"
])
results = processor.export_results("/path/to/output")
Custom Plugins
python
# Create custom analysis plugin
from dicom3d_viewer.plugins import AnalysisPlugin

class CustomAnalysis(AnalysisPlugin):
    def __init__(self):
        super().__init__("Custom Analysis", "1.0")
    
    def process(self, image_data):
        # Your custom analysis here
        return results
⚙️ Configuration
Settings File (config.json)
json
{
  "rendering": {
    "default_renderer": "volume",
    "background_color": [0.1, 0.1, 0.2],
    "interactive_update": true
  },
  "display": {
    "window_width": 400,
    "window_level": 40,
    "interpolation": "linear"
  },
  "export": {
    "default_format": "PNG",
    "image_quality": 95,
    "include_annotations": true
  },
  "performance": {
    "max_memory_usage": "4GB",
    "gpu_acceleration": true,
    "multiprocessing": true
  }
}
Keyboard Shortcuts
Action	Shortcut
Open DICOM File	Ctrl+O
Open DICOM Directory	Ctrl+D
Save Screenshot	Ctrl+S
Toggle Fullscreen	F11
Reset View	R
Window/Level	Ctrl+Mouse Drag
Next Image	→ or Page Down
Previous Image	← or Page Up
Zoom In	+ or Ctrl+Wheel Up
Zoom Out	- or Ctrl+Wheel Down
🏥 Medical Use Cases
Radiology
CT Scan Analysis: Bone, soft tissue, and organ visualization
MRI Interpretation: Brain, spine, and joint imaging
Angiography: Vessel analysis and stenosis detection
Cardiac Imaging: Heart structure and function assessment
Surgery Planning
3D Reconstruction: Create 3D models for surgical planning
Anatomical Measurements: Precise pre-operative measurements
Implant Planning: Orthopedic and dental implant positioning
Tumor Localization: Identify and measure lesions
Education & Research
Medical Training: Interactive anatomy visualization
Case Studies: Compare normal and pathological images
Research Analysis: Quantitative image analysis for studies
Publication Figures: Generate high-quality medical illustrations
🔬 Technical Specifications
Supported Formats
DICOM: All standard DICOM formats
NIFTI: Neuroimaging formats (.nii, .nii.gz)
MetaImage: .mhd/.raw files
VTK Legacy: .vtk files
NRRD: Nearly Raw Raster Data
Performance
Memory Efficient: Handles large datasets (>1GB)
GPU Accelerated: OpenGL-based rendering
Multi-threaded: Parallel processing for analysis
Scalable: From single slices to whole-body scans
Standards Compliance
DICOM 3.0: Full compliance with medical imaging standards
HIPAA Ready: Privacy and security considerations
IHE Compatible: Integration with healthcare enterprise systems
🤝 Contributing
We welcome contributions from the medical imaging community!

Areas for Contribution
New Analysis Tools: Implement advanced measurement algorithms
Rendering Improvements: Enhance visualization techniques
Format Support: Add support for additional medical imaging formats
Performance Optimization: Improve speed and memory usage
UI/UX Enhancement: Better user interface design
Documentation: Improve guides and tutorials
Development Setup
bash
# Fork and clone the repository
git clone https://github.com/YOUR_USERNAME/Dicom3D-Viewer.git
cd Dicom3D-Viewer

# Install development dependencies
pip install -r requirements-dev.txt

# Run tests
python -m pytest tests/

# Start development server
python -m dicom3d_viewer --dev
📋 Roadmap
Version 2.0 (Planned)
 AI Integration: Machine learning-based organ segmentation
 Cloud Support: Load DICOM from PACS servers
 Advanced Measurements: Curved reformatting and advanced metrics
 Collaboration Tools: Share views and annotations
 Mobile Companion: iOS/Android app for basic viewing
Version 2.5 (Future)
 Real-time Processing: Live image enhancement and filtering
 VR Support: Virtual reality viewing capabilities
 Multi-user Sessions: Collaborative analysis sessions
 Automated Reporting: AI-generated diagnostic reports
⚖️ Legal & Compliance
Medical Device Classification
This software is intended for educational and research purposes. It is NOT classified as a medical device and should NOT be used for clinical diagnosis without proper validation and regulatory approval.

DICOM Privacy
Automatic anonymization tools included
PHI (Protected Health Information) handling guidelines
Secure data transmission capabilities
Audit trail functionality
Regulatory Notes
FDA compliance considerations for commercial use
CE marking requirements for European markets
Local regulatory requirements may apply
📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

Important: While the software is open source, medical use requires appropriate validation and may be subject to local regulations.

🙏 Acknowledgments
VTK Community: For powerful 3D visualization capabilities
PyQt Team: For robust GUI framework
DICOM Standard Committee: For medical imaging standards
Medical Imaging Community: For feedback and contributions
Open Source Contributors: For ongoing development support
📞 Support & Contact
Documentation
User Manual: docs/user-manual.md
API Reference: docs/api-reference.md
Tutorials: docs/tutorials/
Community
GitHub Issues: Report bugs and request features
Discussions: Join the community
Wiki: Community knowledge base
Professional Support
Commercial Licenses: Available for commercial use
Custom Development: Tailored solutions for specific needs
Training Sessions: Professional training available
Validation Services: Regulatory compliance assistance
Made with ❤️ by Sohaila Emad

DICOM 3D Viewer - Professional Medical Imaging Visualization

⚠️ Medical Disclaimer: This software is for educational and research purposes only. Not intended for clinical diagnosis. Always consult with qualified medical professionals for medical decisions.

