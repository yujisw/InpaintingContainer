FROM python:3.7

# opencv-devのインストール
RUN apt-get update -y && apt-get install -y libopencv-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ENV APP_NAME inpaint

WORKDIR /home/$APP_NAME
# WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# COPY . .

# CMD [ "/bin/bash" ]
# CMD [ "python", "./test.py" ]