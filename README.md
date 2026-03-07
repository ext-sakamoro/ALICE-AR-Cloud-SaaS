# ALICE-AR-Cloud

AR/VR cloud rendering with spatial synchronization and SDF geometry

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum |

## ALICE Crate Integration

alice-sdf, alice-view, alice-streaming-protocol, alice-presence, alice-space

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST` | `/api/v1/scene` | 3Dシーン構築（SDF） |
| `POST` | `/api/v1/stream` | ストリーミングセッション開始 |
| `POST` | `/api/v1/anchor` | 空間アンカー設置 |
| `GET ` | `/api/v1/presence` | 接続ユーザー状態 |
| `GET ` | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
