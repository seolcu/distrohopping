# KDE Sunshine 설정

Sunshine 원격 스트리밍 시 디스플레이 전환을 위한 스크립트.

## 스트리밍 시작 시 (Do Command)

```bash
sh -c "kscreen-doctor output.DP-1.disable output.HDMI-A-2.enable output.HDMI-A-2.mode.${SUNSHINE_CLIENT_WIDTH}x${SUNSHINE_CLIENT_HEIGHT}@${SUNSHINE_CLIENT_FPS}"
```

## 스트리밍 종료 시 (Undo Command)

```bash
kscreen-doctor output.DP-1.enable output.HDMI-A-2.disable
```
