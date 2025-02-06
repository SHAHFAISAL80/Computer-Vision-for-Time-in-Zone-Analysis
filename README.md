# Computer-Vision-for-Time-in-Zone-Analysis

time in zone
YouTube

👋 hello
Practical demonstration on leveraging computer vision for analyzing wait times and monitoring the duration that objects or individuals spend in predefined areas of video frames. This example project, perfect for retail analytics or traffic management applications.

clone repository and navigate to example directory

git clone --depth 1 -b develop https://github.com/roboflow/supervision.git
cd supervision/examples/time_in_zone
setup python environment and activate it [optional]

python3 -m venv venv
source venv/bin/activate
install required dependencies

pip install -r requirements.txt
🛠 scripts
download_from_youtube
This script allows you to download a video from YouTube.

--url: The full URL of the YouTube video you wish to download.
--output_path (optional): Specifies the directory where the video will be saved.
--file_name (optional): Sets the name of the saved video file.
python scripts/download_from_youtube.py \
    --url "https://www.youtube.com/watch?v=-8zyEwAa50Q" \
    --output_path "data/checkout" \
    --file_name "video.mp4"
python scripts/download_from_youtube.py \
    --url "https://www.youtube.com/watch?v=MNn9qKG2UFI" \
    --output_path "data/traffic" \
    --file_name "video.mp4"
stream_from_file
This script allows you to stream video files from a directory. It's an awesome way to mock a live video stream for local testing. Video will be streamed in a loop under rtsp://localhost:8554/live0.stream URL. This script requires docker to be installed.

--video_directory: Directory containing video files to stream.
--number_of_streams: Number of video files to stream.
python scripts/stream_from_file.py \
    --video_directory "data/checkout" \
    --number_of_streams 1
python scripts/stream_from_file.py \
    --video_directory "data/traffic" \
    --number_of_streams 1
draw_zones
If you want to test zone time in zone analysis on your own video, you can use this script to design custom zones and save results as a JSON file. The script will open a window where you can draw polygons on the source image or video file. The polygons will be saved as a JSON file.

--source_path: Path to the source image or video file for drawing polygons.

--zone_configuration_path: Path where the polygon annotations will be saved as a JSON file.

enter - finish drawing the current polygon.

escape - cancel drawing the current polygon.

q - quit the drawing window.

s - save zone configuration to a JSON file.

python scripts/draw_zones.py \
    --source_path "data/checkout/video.mp4" \
    --zone_configuration_path "data/checkout/config.json"
python scripts/draw_zones.py \
    --source_path "data/traffic/video.mp4" \
    --zone_configuration_path "data/traffic/config.json"
