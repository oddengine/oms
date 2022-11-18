# oms

Odd Media Server is not only a modern Live Streaming Server, but also a WebRTC SFU.

## Platform

| Windows | Linux | Mac OS |
| :--- | :--- | :--- |
| √ | √ | √ |

## Protocol

| Protocol | RTMP | HTTP/WS-FLV | HTTP/WS-FMP4 | HLS (MPEG-TS) | HLS-2nd (CMAF) | MPEG-DASH (CMAF) | RTSP | WebRTC |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Input | √ |  |  |  |  |  |  | √ |
| Output | √ | √ | √ | √ | √ | √ |  | √ |

## Codec

| Protocol | RTMP | HTTP/WS-FLV | HTTP/WS-FMP4 | HLS (MPEG-TS) | HLS-2nd (CMAF) | MPEG-DASH (CMAF) | RTSP | WebRTC |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| AAC | √ | √ | √ | √ | √ | √ |  |  |
| AVC | √ | √ | √ | √ | √ | √ |  | √ |
| Opus |  |  |  |  |  |  |  | √ |
| VP8 |  |  |  |  |  |  |  | √ |

## Run

```code
nohup ./daemon.sh >/dev/null 2>&1 &
```
