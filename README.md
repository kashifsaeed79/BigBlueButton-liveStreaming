# BBB Live Streaming

Streams a given BBB Meeting to an RTMP Server.

## Getting Started

### Prerequisites

All you need is Docker running on your machine and a media server to stream to.

### Configuration

You need to set some environment variables to run the container.

#### Required
* BBB_URL - URL to BBB including http/https e.g. https://your_BigBlueButton_server/bigbluebutton/api
* BBB_MEETING_ID - ID of the BBB Meeting (You can get the ID via an API call: https://your_bbb_server/bigbluebutton/api/getMeetings?checksum=<checksum>)
* BBB_SECRET - Secret of your BBB installation (You can get the secret with: bbb-conf --secret)
* BBB_STREAM_URL - Stream URL to your streaming server including rtmp. (e.g. rtmp://media_server_url/stream/stream_key)

#### Optional
* BBB_AS_MODERATOR - if set to "true" the meeting will be joined as moderator
* BBB_USER_NAME - the Username to join the meeting. (Default: Live)

### Starting liveStreaming
* wget -O docker-compose.yml https://github.com/aau-zid/BigBlueButton-liveStreaming/raw/master/docker-compose.yml.example
* (change configuration)
* docker-compose up -d
* docker-compose down

## Known Limitations
* You must extract and provide the meetingID, which is not visible within the room.
* Some unnecessary html elements are not hidden yet.
* ffmpeg settings to be improved
