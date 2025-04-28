# AI Video Background Customization System

![Demo Interface]

A real-time video processing solution using YOLOv8 segmentation for professional background manipulation, featuring multiple background modes and optimized performance.

## Features ✨

- **Real-time Background Customization**
  - Blur background with adjustable strength
  - Replace with custom image (default provided)
  - Complete background removal (black)
- **Multi-device Support**
  - Automatic camera detection
  - Virtual camera output
- **Performance Optimized**
  - GPU acceleration support (CUDA/MPS)
  - Configurable FPS (1-1000)
- **Modern Web Interface**
  - Responsive design
  - Real-time controls
  - Device status monitoring

## Tech Stack 🛠️

- **Backend**: FastAPI, Python 3.9
- **AI Engine**: YOLOv8 Segmentation
- **Frontend**: HTML5, CSS3, JavaScript
- **Virtual Camera**: pyvirtualcam
- **Docker**: Containerization support

## Installation 📦

### Prerequisites
- Python 3.9+
- Webcam device
- NVIDIA GPU (optional for CUDA acceleration)

### Local Setup

1. **Clone Repository**
   ```bash
   git clone https://github.com/username/sakshamtapadia-video-broadcaster.git
   cd sakshamtapadia-video-broadcaster
   ```

2. **Setup Environment**
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # Linux/Mac
   .venv\Scripts\activate    # Windows
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Add Static Assets**
   - Place `logo.jpg` (300x300) and `wallhaven.png` (1920x1080) in `/static`
   - Or use default placeholder images

### Docker Setup

1. **Build Container**
   ```bash
   docker build -t video-broadcaster .
   ```

2. **Run Container**
   ```bash
   docker run -p 8000:8000 --device=/dev/video0 video-broadcaster
   ```

## Usage 🖥️

1. **Start Application**
   ```bash
   python main.py
   ```
   Access interface at `http://localhost:8000`

2. **Web Interface Controls**
   - Select camera device from dropdown
   - Configure settings:
     - FPS (1-1000)
     - Blur strength (1-51 odd numbers)
     - Background mode (Blur/None/Default)
   - Start/Stop streaming

3. **Virtual Camera Output**
   - Use virtual camera in video conferencing apps
   - Select "OBS Virtual Camera" as video source

## Configuration ⚙️

| Parameter        | Range         | Default | Description                |
|------------------|---------------|---------|----------------------------|
| `fps`            | 1-1000        | 15      | Output frame rate          |
| `blur_strength`  | 1-51 (odd)    | 21      | Gaussian blur kernel size  |
| `background`     | blur/none/default | blur | Background mode       |

## Project Structure 📂

```
sakshamtapadia-video-broadcaster/
├── Dockerfile
├── LICENSE
├── README.md
├── engine.py            # AI segmentation engine
├── main.py              # FastAPI application
├── requirements.txt
├── stream_utils.py      # Video streaming pipeline
├── utils.py
└── static/
    ├── index.html       # Modern UI
    ├── logo.jpg         Application logo
    └── wallhaven.png    Default background
```

## Troubleshooting 🔧

**Common Issues:**

```bash
# Webcam not detected
ERROR: Camera list empty
SOLUTION: Check OS permissions for camera access

# Missing static assets
ERROR: 404 on /static/logo.jpg
SOLUTION: Add required files to static/ directory

# CUDA Out of Memory
ERROR: GPU memory allocation failed
SOLUTION: Reduce frame resolution or upgrade GPU
```

## License 📄

MIT License - See [LICENSE](LICENSE) for details

---

**Support**  
For assistance, open a GitHub issue with:
1. Error logs
2. Reproduction steps
3. Hardware specifications (CPU/GPU/RAM)
```
