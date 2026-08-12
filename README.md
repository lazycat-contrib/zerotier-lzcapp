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

## Publishing

GitHub Actions builds the LPK, creates the versioned GitHub Release asset
`community.lazycat.app.zerotier-v1.16.0.lpk`, and reconciles the same verified
package with both the LazyCat official store and the MiaoMiao private store.
Generated LPK files are not committed to Git.

## Note

ZeroTier is a VPN service that requires host network mode and special device access. The network ID must be provided by the user during deployment.# zerotier-lzcapp
