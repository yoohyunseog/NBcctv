# CCTV 감시 시스템

실시간 CCTV 카메라 모니터링 웹 애플리케이션입니다.

## 기능

- 📹 **다중 카메라 지원**: 최대 10개 이상의 카메라 동시 모니터링
- 🎥 **다양한 스트림 형식 지원**:
  - HTTP/MJPEG 스트림
  - HLS 스트림 (.m3u8)
  - 일반 비디오 파일 (MP4 등)
  - RTSP (안내 메시지 표시)
- 🖼️ **그리드 레이아웃**: 반응형 그리드로 여러 카메라를 한눈에 확인
- 🔍 **전체화면 보기**: 개별 카메라를 전체화면으로 확대
- ✏️ **카메라 관리**: 추가, 수정, 삭제 기능
- 💾 **로컬 저장**: 브라우저 로컬 스토리지에 카메라 설정 저장
- 🔄 **실시간 새로고침**: 전체 카메라 새로고침 기능

## 사용 방법

1. `index.html` 파일을 브라우저에서 엽니다.
2. 기본적으로 10개의 예시 카메라가 표시됩니다.
3. **카메라 추가** 버튼을 클릭하여 새로운 카메라를 추가합니다.
4. 각 카메라의 **수정** 버튼으로 카메라 정보를 변경할 수 있습니다.
5. **확대** 버튼으로 전체화면으로 카메라를 볼 수 있습니다.

## 카메라 URL 형식

### HTTP/MJPEG 스트림
```
http://카메라IP:포트/video
http://카메라IP:포트/mjpeg
```

### HLS 스트림
```
http://카메라IP:포트/stream.m3u8
```

### 스냅샷 (정적 이미지)
```
http://카메라IP:포트/snapshot.jpg
```

### 일반 비디오
```
http://서버/비디오파일.mp4
```

### RTSP (참고)
RTSP 스트림은 웹 브라우저에서 직접 재생할 수 없습니다. 
백엔드 서버를 통해 WebRTC나 HLS로 변환해야 합니다.

## 주요 카메라 제조사별 URL 예시

### Hikvision
- MJPEG: `http://username:password@ip:port/Streaming/channels/1/picture`
- RTSP: `rtsp://username:password@ip:554/Streaming/Channels/101`

### Dahua
- MJPEG: `http://username:password@ip:port/cgi-bin/snapshot.cgi`
- RTSP: `rtsp://username:password@ip:554/cam/realmonitor?channel=1&subtype=0`

### Axis
- MJPEG: `http://ip:port/mjpg/video.mjpg`
- RTSP: `rtsp://ip:554/axis-media/media.amp`

## 고급 기능 (향후 추가 가능)

- [ ] RTSP → WebRTC 변환 서버 연동
- [ ] 녹화 기능
- [ ] 모션 감지 알림
- [ ] 타임라인 재생
- [ ] 다중 사용자 지원
- [ ] 권한 관리

## 기술 스택

- HTML5
- CSS3 (Grid Layout, Flexbox)
- Vanilla JavaScript
- LocalStorage API

## 브라우저 호환성

- Chrome/Edge (권장)
- Firefox
- Safari
- Opera

## 보안 참고사항

- 실제 운영 환경에서는 HTTPS를 사용하세요.
- 카메라 인증 정보는 안전하게 관리하세요.
- CORS 설정이 필요한 경우 서버에서 허용해야 합니다.

## 문제 해결

### 카메라가 표시되지 않는 경우
1. 카메라 URL이 올바른지 확인
2. 네트워크 연결 확인
3. 브라우저 콘솔에서 오류 메시지 확인
4. CORS 문제인 경우 서버 설정 확인

### RTSP 스트림 재생이 안 되는 경우
- RTSP는 웹 브라우저에서 직접 재생 불가
- 백엔드 서버(FFmpeg, MediaMTX 등)를 통해 변환 필요

## 라이선스

이 프로젝트는 자유롭게 사용 가능합니다.

