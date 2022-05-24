# Intel OpenVino passenger_counter_app

### Prerequisites : 

1) Ubuntu 18.04
2) Python 3.6
3) OpenVino toolkit 2020.3

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

i)open mosca 

1) sudo lsof -i:3000
2) cd webservice/server/node-server
3) node ./server.js


ii)open the gui

1) cd ../../ui
2) npm run dev

iii) openning ffpeg server

1) cd ../..
2) sudo ffserver -f ./ffmpeg/server.conf

iv) run using python script

1) source /opt/intel/openvino/bin/setupvars.sh
2) source openvino_env/bin/activate
3) cd ./applications
4) python3 people_counter.py -m /opt/intel/openvino/deployment_tools/open_model_zoo/tools/downloader/intel/person-detection-retail-0013/FP32/person-detection-retail-0013.xml -d CPU -pt 0.6 | ffmpeg -v warning -f rawvideo -pixel_format bgr24 -video_size 768x432 -framer


