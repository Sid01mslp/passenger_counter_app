# passenger_counter_app

### Prerequisites : 

1) Ubuntu 18.04
2) Python 3.6
3)OpenVino toolkit 2020.3

./setup.sh

node -v == 6.17.1
npm -v ==3.10.10

sudo npm install -g n
sudo n 6.17.1

clone : https://github.com/Sid01mslp/passenger_counter_app

install other dependencies:
cd webservice/server
npm install
npm i jsonschema@1.2.6

cd ../ui
npm install


Now Run the applications step: 
1) sudo lsof -i:3000
cd webservice/server/node-server
node ./server.js

2) cd ../../ui
npm run dev

3) cd ../..
sudo ffserver -f ./ffmpeg/server.conf

4) source /opt/intel/openvino/bin/setupvars.sh

python3 people_counter.py -m /opt/intel/openvino/deployment_tools/open_model_zoo/tools/downloader/intel/person-detection-retail-0013/FP32/person-detection-retail-0013.xml -d CPU -pt 0.6 | ffmpeg -v warning -f rawvideo -pixel_format bgr24 -video_size 768x432 -framer
