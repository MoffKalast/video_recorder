# video_record

A fork of https://github.com/ildoonet/ros-video-recorder.

### Usage

    roslaunch video_recorder record.launch video_path:=/home/ubuntu/[timestamp].avi

### Parameters

+ ~output_width(int: default 640) : Output video width.
+ ~output_height(int: default 480) : Output video height.
+ ~output_fps(int: default 30) : Output video fps(frame per seconds).
+ ~output_format(str: default xvid) : Output video format in fourcc format. See [FourCC Identifier](https://www.fourcc.org/codecs.php)
+ ~output_path(str) : Output Video File Path. eg: /home/ildoonet/Documents/video.mp4
  + [timestamp] : will be replaced with real timestamp. eg. grid_[timestamp].mp4 ---> grid_20170626_185926.mp4
+ ~output_topic(str) : Broadcast Output Video, if provided. eg. /image_recorder/image_raw

+ ~source1(str) : Incoming Video Frame Info in Format(topic,target_x,target_y,target_w,target_h)
  + eg: "/cv_camera/image_raw,0,0,320,240"
  + Source image will be resized automatically at target_w, target_h
  + Resized image will be pasted at the position of (target_x, target_y)
  + ~source{n} : n is {1, 2, 3, ...}.
