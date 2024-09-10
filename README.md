import cv2 as cv
import numpy as np

video = []
capture = cv.VideoCapture(0)

while True:
    isTrue, frame = capture.read()
    frame = cv.resize(frame, (1200, 800), interpolation=cv.INTER_AREA)
    cv.imshow("Display Video", frame)
    video.append(frame)
    if cv.waitKey(1) & 0xFF==ord('d'):
        break
capture.release()
cv.destroyAllWindows()

play=input("Want to play the video???? press 'p' ")
if(play=="p"):
    for video in video:
        # video2 = cv.cvtColor(video, cv.COLOR_BGR2GRAY)
        video = cv.resize(video, (1200, 800), interpolation=cv.INTER_AREA)
        cv.imshow("Video", video)
        cv.waitKey(40)
