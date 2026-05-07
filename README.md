# traffic_violation
This is computer vision pipeline which uses YOLOv8 for object detection and  custom logic for the recognition of traffic violations such as no helmet, triple riding and uses TrOCR to read the number plate of the violating vehicles and stores them along with time stamps in the SQLite databbase.

## Pipeline

1. YOLOv8 processes every 30th frame of the input video  
2. Helmet Check  
   - Matches helmet to rider and flags no-helmet riders  
3. Triple riding  
   - Groups riders near the bike; if >= 3, flags violation  
4. Number plate preprocessing using OpenCV  
   - bilateralFilter, sharpening, CLAHE  
5. Processed image is passed to TrOCR for OCR  
6. Validated with Indian plate regex and saved

    # Demo
  <img width="1124" height="756" alt="image" src="https://github.com/user-attachments/assets/a21540ff-6f53-4a8b-8bcd-e1dfaf69bf47" />
 
 # Database table(SQLite)
 <img width="1406" height="886" alt="image" src="https://github.com/user-attachments/assets/93e35ce9-2f84-4a19-ad26-2b9f15df4d93" />
# Live Demo : https://huggingface.co/spaces/varshi0905/traffic_violation_detection
