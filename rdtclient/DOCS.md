# RDT-Client

## About

[RDT-Client](https://github.com/rogerfar/rdt-client) is a web-based torrent
management interface for debrid services. It downloads torrents via your debrid
account and saves them to a local path of your choice.

Supported debrid services:
- Real-Debrid
- AllDebrid
- Premiumize
- TorBox
- DebridLink

It also provides a fake qBittorrent API, making it compatible with Sonarr,
Radarr, and other *arr tools.

## Installation

1. Add this repository to your Home Assistant add-on store
2. Install the "RDT-Client" add-on
3. Configure timezone in the add-on options
4. Start the add-on
5. Click "Open Web UI" to access the interface on port 6500
6. Create your account and connect your debrid service

## Configuration

### Option: `TZ`

Timezone for the container. Default: `Europe/Prague`.
Example values: `Europe/London`, `America/New_York`, `Asia/Tokyo`.

## Setting Up Downloads

After the first start, configure the download path in the rdt-client web UI:

1. Open the Web UI (port 6500)
2. Go to **Settings**
3. Set the download path to a location under `/media` (e.g., `/media/downloads`)
   or `/share` (e.g., `/share/downloads`)
4. Files saved to `/media` are accessible via Home Assistant's Media Browser
5. Files saved to `/share` are accessible by other add-ons

## Sonarr / Radarr Integration

RDT-Client exposes a fake qBittorrent API:

1. In Sonarr/Radarr, add a new **Download Client**
2. Select **qBittorrent**
3. Set **Host** to your Home Assistant IP address
4. Set **Port** to `6500`
5. Enter the username and password you created in rdt-client
6. Test the connection

## Data Persistence

- **Database**: Stored in `/data/db` (persisted across add-on restarts and updates)
- **Downloads**: Stored at the path you configure in rdt-client UI

## Support

For issues with this add-on:
https://github.com/keeema/hassio-addons/issues

For issues with rdt-client itself:
https://github.com/rogerfar/rdt-client
