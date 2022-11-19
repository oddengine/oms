# Live Streaming Server

## Protocols

|  | Input | Output |
| :--- | :--- | :--- |
| RTMP | √ | √ |
| RTSP | √ |  |
| HTTP/WS-FLV |  | √ |
| HTTP/WS-FMP4 |  | √ |
| HLS (MPEG-TS) |  | √ |
| HLS-2nd (CMAF) |  | √ |
| MPEG-DASH (CMAF) |  | √ |

## Codecs

|  | AAC | H264 |
| :--- | :--- | :--- |
| RTMP | √ | √ |
| RTSP | √ | √ |
| HTTP/WS-FLV | √ | √ |
| HTTP/WS-FMP4 | √ | √ |
| HLS (MPEG-TS) | √ | √ |
| HLS-2nd (CMAF) | √ | √ |
| MPEG-DASH (CMAF) | √ | √ |

## Media Recorders

| FLV | MPEG-TS | CMAF |
| :--- | :--- | :--- |
| √ | √ | √ |

## Roadmap

- [x] v1.4.06 - Fixed parsing aac channel config.  
- [x] v1.4.31 - Fix rtmp proxy.  
- [x] v1.4.63 - Fix processing rtmp message with fmt=3.  
- [ ] Support RTSP input/output.  
- [ ] Support WebRTC input/output.  