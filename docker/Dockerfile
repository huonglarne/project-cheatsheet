FROM pytorch/pytorch:1.11.0-cuda11.3-cudnn8-runtime AS base
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install ffmpeg python3-opencv -y \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install -r requirements.txt && rm -rf requirements.txt

WORKDIR /src
COPY . .

EXPOSE 5678

### Debug

FROM base AS debug

RUN pip install debugpy

WORKDIR /folder

CMD ["python", "-m", "debugpy", "--listen", "0000:5678", "--wait-for-client", "file.py", "--argument"]