import cv2

# set input and output video paths
input_path = "input_video.mkv"
output_path = "output.mp4"

# open input video
cap = cv2.VideoCapture(input_path)

# get input video properties
fps = cap.get(cv2.CAP_PROP_FPS)
width = int(cap.get(cv2.CAP_PROP_FRAME_WIDTH))
height = int(cap.get(cv2.CAP_PROP_FRAME_HEIGHT))

# set output video properties
fourcc = cv2.VideoWriter_fourcc(*'mp4v')
out = cv2.VideoWriter(output_path, fourcc, fps, (width, height))

# read and write every 4th frame
frame_count = 0
while cap.isOpened():
    ret, frame = cap.read()
    if not ret:
        break
    
    if frame_count % 4 == 0:
        out.write(frame)
    
    frame_count += 1


cap.release()
out.release()
cv2.destroyAllWindows()
