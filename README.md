# ZeroTier - LazyCat App Package

## Files Generated

| File | Description |
|------|-------------|
| `package.yml` | Package metadata (LPK v2 format) |
| `lzc-manifest.yml` | Runtime configuration |
| `lzc-build.yml` | Build configuration |
| `lzc-deploy-params.yml` | User deployment parameters |

## Configuration

- **Image**: `zyclonite/zerotier:router`
- **Network Mode**: Host (VPN service)
- **Data Path**: `/lzcapp/var/zerotier`

## User Parameters

| Parameter | Description |
|-----------|-------------|
| `zerotier_network_id` | ZeroTier network ID to join |

## Special Handling

This app uses `compose_override` to handle:
- Device binding: `/dev/net/tun`
- Capabilities: `NET_ADMIN`, `SYS_ADMIN`, `NET_RAW`

## Next Steps

1. **Add icon**: Place a 512x512 PNG icon as `icon.png`
2. **Build**: `lzc-cli project release -o zerotier.lpk`
3. **Publish**: `lzc-cli appstore publish zerotier.lpk`

## Note

ZeroTier is a VPN service that requires host network mode and special device access. The network ID must be provided by the user during deployment.# zerotier-lzcapp
