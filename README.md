# traffic_violation
This is computer vision pipeline which uses YOLOv8 for object detection and  custom logic for the recognition of traffic violations such as no helmet, triple riding and uses TrOCR to read the number plate of the violating vehicles and stores them along with time stamps in the SQLite databbase.

# Pipeline
 1.The YOLOv8 processes every 30th frame of the input video </n>
 2.Helmet Check:
      It matches helmet to rider and flags no helemt riders
 3.Triple riding:
      It groups the riders nearby the bike. If these riders are 3 or more it flags them.
  4. The number plate of these violated vehicles is taken. And thsi image of the number plate is preprocessed with different OPEN CV image processing techniques like bilateralFilter, sharpening, and CLAHE for efficient OCR by TrOCR.
  5. This processes image is now used by the TrOCR for OCR.
  6. The detected number is validated with Indian Plate recognition regex. If the plate is validated teh image of theviolation gets saved in the file specified and the database is also saved
 
 # Demo
  <img width="1124" height="756" alt="image" src="https://github.com/user-attachments/assets/a21540ff-6f53-4a8b-8bcd-e1dfaf69bf47" />
 
 # Database table(SQLite)
 <img width="1406" height="886" alt="image" src="https://github.com/user-attachments/assets/93e35ce9-2f84-4a19-ad26-2b9f15df4d93" />
