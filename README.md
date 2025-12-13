# joint-kinematics-analysis
# 🏃‍♂️ Sport Performance Pose Estimation Analyzer

A real-time biomechanics analysis tool for sports performance using AI-powered pose estimation. This application supports high-speed video capture (up to 240 FPS) and provides instant feedback on joint angles, linear kinematics, and angular velocities.

![Sport Performance Analyzer](https://img.shields.io/badge/TensorFlow.js-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)

## ✨ Features

### 📹 High-Speed Video Support
- **30 FPS** - Standard frame rate for basic analysis
- **60 FPS** - High frame rate for detailed movements
- **120 FPS** - Very high frame rate for fast sports movements
- **240 FPS** - Ultra-high frame rate for explosive movements
- Real-time FPS detection and display

### 👥 Participant Management
- Collect data from up to **10 participants**
- Required participant information:
  - Name
  - Sex (Male/Female/Other)
  - Age (years)
  - Mass (kg)
  - Height (cm)
- Height-based calibration for accurate real-world measurements
- Multiple recording sessions per participant

### 📊 Real-Time Biomechanics Metrics

#### Linear Kinematics
- **Linear Displacement** (meters) - Total distance traveled
- **Linear Velocity** (m/s) - Speed of movement

#### Angular Kinematics
- **Knee Angle** (degrees) - Hip-Knee-Ankle angle
- **Elbow Angle** (degrees) - Shoulder-Elbow-Wrist angle
- **Hip Angle** (degrees) - Shoulder-Hip-Knee angle
- **Angular Velocity** (°/s) - Rate of joint angle change

### 💾 Data Export
- Download all participant data in **XLSX (Excel)** format
- Separate sheets for each participant
- Frame-by-frame data including:
  - Timestamps
  - Joint angles
  - Position coordinates
  - Recording metadata (FPS, date/time)

### 🎨 User Interface
- Modern gradient design
- Real-time skeleton visualization overlaid on video
- Live metrics dashboard
- Responsive layout for different screen sizes

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome, Edge, or Firefox recommended)
- Webcam or external camera
- Internet connection (for loading AI models)

### Installation

1. **Download the HTML file**
   ```bash
   git clone https://github.com/yourusername/sport-pose-estimation.git
   cd sport-pose-estimation
   ```

2. **Open the file**
   - Simply open `pose-estimation.html` in your web browser
   - No installation or build process required!

### Alternative: Use GitHub Pages

1. Fork this repository
2. Go to Settings → Pages
3. Select main branch as source
4. Access your app at `https://yourusername.github.io/sport-pose-estimation/pose-estimation.html`

## 📖 How to Use

### Step 1: Add Participants
1. Fill in participant information (all fields required)
2. Click "Add Participant"
3. Repeat for up to 10 participants

### Step 2: Configure Camera
1. Select desired frame rate (120 or 240 FPS recommended for sports)
2. Click "Start Camera"
3. Allow browser to access your camera when prompted
4. Wait for AI model to load (first time only)

### Step 3: Record Movement
1. Select a participant from the dropdown menu
2. Position the athlete in view of the camera
3. Click "Start Recording"
4. Perform the athletic movement
5. Click "Stop Recording" when complete
6. Repeat for multiple trials or different participants

### Step 4: Export Data
1. Click "📊 Download All Data (XLSX)"
2. Open the Excel file to analyze frame-by-frame data
3. Use the data for biomechanical analysis, research, or coaching

## 🔬 Technical Details

### Technologies Used
- **TensorFlow.js** (v4.11.0) - Machine learning framework
- **MoveNet** - Fast and accurate pose detection model
- **SheetJS (XLSX)** (v0.18.5) - Excel file generation
- **HTML5 Canvas** - Real-time visualization
- **MediaDevices API** - Camera access and high FPS capture

### Pose Detection
- Uses Google's MoveNet SinglePose Lightning model
- 17 keypoint detection (nose, eyes, ears, shoulders, elbows, wrists, hips, knees, ankles)
- Confidence threshold: 0.3 (30%)
- Real-time processing at up to 60+ FPS on modern hardware

### Calibration System
The system uses participant height for automatic calibration:
- Converts pixel measurements to real-world meters
- Formula: `pixelsToMeters = (height_cm / 100) / canvas_height_pixels`
- Provides accurate displacement and velocity calculations

### Data Structure
Exported Excel files contain:
```
Sheet per participant:
├── Participant Information
│   ├── Name, Sex, Age, Mass, Height
├── Recording 1
│   ├── Timestamp, FPS
│   ├── Frame-by-frame data
│   │   ├── Frame number
│   │   ├── Timestamp (ms)
│   │   ├── Knee Angle (°)
│   │   ├── Elbow Angle (°)
│   │   ├── Hip Position (x, y)
├── Recording 2...
```

## 🎯 Use Cases

- **Sports Performance Analysis** - Track joint angles during athletic movements
- **Rehabilitation Monitoring** - Measure range of motion improvements
- **Coaching & Training** - Provide objective feedback to athletes
- **Biomechanics Research** - Collect kinematic data for studies
- **Physical Education** - Teach proper movement patterns
- **Injury Prevention** - Identify potentially harmful movement patterns

## 🔧 Troubleshooting

### Camera Not Starting
- **Check permissions**: Ensure browser has camera access
- **Try different browser**: Chrome and Edge have best camera API support
- **Check camera connection**: Ensure camera is properly connected and not in use

### Low FPS Performance
- **Close other applications**: Free up system resources
- **Use better lighting**: Improves pose detection accuracy
- **Reduce video quality**: Lower resolution may improve FPS
- **Use modern hardware**: Older computers may struggle with 120-240 FPS

### Pose Not Detected
- **Improve lighting**: Ensure subject is well-lit
- **Check distance**: Stand 2-4 meters from camera
- **Wear contrasting clothing**: Helps with detection
- **Ensure full body visible**: All joints should be in frame

### Excel Export Issues
- **Check browser compatibility**: Use modern browser
- **Allow downloads**: Ensure browser allows file downloads
- **Record some data first**: Cannot export if no recordings exist

## 📝 Browser Compatibility

| Browser | Status | Notes |
|---------|--------|-------|
| Chrome 90+ | ✅ Recommended | Best performance |
| Edge 90+ | ✅ Recommended | Best performance |
| Firefox 88+ | ✅ Supported | Good performance |
| Safari 14+ | ⚠️ Limited | May have FPS limitations |
| Mobile Browsers | ⚠️ Limited | Not optimized for mobile |

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- **TensorFlow.js Team** - For the amazing ML framework
- **Google Research** - For the MoveNet pose estimation model
- **SheetJS** - For the Excel file generation library

## 📧 Contact

For questions, issues, or suggestions:
- Open an issue on GitHub
- Email: your.email@example.com
- Twitter: @yourusername

## 🔮 Future Enhancements

- [ ] Multi-person pose detection
- [ ] 3D pose estimation
- [ ] Video file upload support
- [ ] More joint angle measurements (ankle, shoulder, etc.)
- [ ] Comparative analysis between participants
- [ ] Real-time angle overlay on video
- [ ] CSV export option
- [ ] Cloud storage integration
- [ ] Mobile app version

## 📊 Version History

### v1.0.0 (Current)
- Initial release
- Basic pose detection
- 10 participant support
- XLSX export
- Real-time metrics display
- 30-240 FPS support

---

**Made with ❤️ for sports science and biomechanics**
