## TODOs

### High Priority
- [-] Receive max of one video stream on mobile / configurable
- [in-progress] Fix issue where iOS 14 disconnects when new tracks are received
  - [in-progress] Fork SimplePeer (client-side) and error logging for all calls to destroy()
  - [-] Use same simple-peer fork on server as in client
  - [done] Implement initiator connection auto-reconnect (see simple-peer "close" in ZenRTCPeer)
- [partially-complete] Implement media stream track synchronization
  See https://www.kevinmoreland.com/articles/03-22-20-webrtc-mediastream-tracks
  See https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/ssrc
  See https://tools.ietf.org/html/rfc3550#section-8
  - [-] DirectAudio / https://www.evernote.com/client/web#?an=true&n=8a027abf-cf90-47a4-88ae-0bac8b391fdf&
  - [in-progress] Multi-client state management (PhantomState)
  - [-] Media stream track "read-receipt" play verification / Remote-play status reporting (i.e. participant B is playing video from participant A)
  - [partially-complete] Force outgoing media stream tracks to end if connection drops
  - [partially-complete] Remove ended tracks from web clients
  - [in-progress] Display mapped tracks in PhantomServer Debugger UI
  - [in-progress] Map MediaStreamTracks to their proxied peers (via participant track map)
  - [partially-complete] Mute / Unmute
    - [-] Unpublish / republish video tracks when mobile browsers go into background / come into foreground
    - [done] Use gain control for muting, instead of track publish / unpublish (too long to negotiate)
    - [done] Fix issue where muting / unmuting can cause duplicated tracks (seems to happen most when doing screen sharing)

### Medium Priority
- [-] Links to open-source projects, tech used, etc.
- [-] Add Quilljs and pair w/ Freesound API to try to create documents w/ sound effects / ability to save / share
- [partially-complete] Posenet models:  https://github.com/tensorflow/tfjs-models/tree/master/posenet/demos
  - [-] Shared w/ other participants
  - [-] Random color for each participant (use participant session color?)
- [-] Add device pairing (paired devices treated as single user to other peers)
- [-] Add menu scrolling (transparent scrollbars?  See https://stackoverflow.com/questions/16670931/hide-scroll-bar-but-while-still-being-able-to-scroll)
- [partially-complete] Implement sound effects / instruments
  - [-] Add ability to sample one instrument and play another (i.e. line-in guitar / piano samples out)
  - [-] Phantom Audio separated by participant (no "sustain" interference)
  - [-] Tone.js library
  - [partially-complete] Loop designer
    - [-] Recording / transposing / instrument switching during playback
  - [partially-complete] Add electric guitar
    - [-] Add more octaves
  - [partially-complete] Add drum samples
  - [partially-complete] Capture keyboard input
    - [done] Basic capture
    - [done] Keydown / up octave switching (springy octave)
    - [-] On-screen keyboard display
  - [done] Left / right key octave switching
  - [done] Add capability / UI for sample switching
- [-] Add CSS classes to header / footer icons and fix their positioning
- [-] Add "flip to main" view functionality and add corresponding button toggle / reset.
- [-] Integration logos
  - [-] Use on opening animation
  - [-] Separate "credits" screen
- [partially-complete] Capture audio levels
  - [partially-complete] Visual indicator
  - [-] Implement pitch detection (https://github.com/cwilso/pitchdetect)
  - [-] Audio waveform visualizors (https://github.com/ehsan/chromium-audio-samples/blob/mozilla/visualizer-live.html)
  - [partially-complete] Improve CPU usage in Firefox (likely via MediaStreamTrackLevelMonitor) 
- [-] Chat messages (convert TTS applet to this?  i.e. options to speak, post to screen, both?)
- [-] Connection "synopsis" text / media description
- [-] View-only mode
- [-] Browserless Clear Linux fork (on zenOSmosis github)
  - [-] Replace base/Dockerfile w/ ClearLinux MediaReferenceStack (https://docs.01.org/clearlinux/latest/guides/stacks/mers.html)
  - [-] Follow instructions for installing Google Chrome on Clear Linux: https://community.clearlinux.org/t/installing-google-chrome-on-clear-linux/1132

-----

- [-] Make Firefox use same font spacing as Chrome in the main menu
- [-] Implement multiple WebRTC data channels: https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Using_data_channels
- [-] React Router for menu functionality / native back button support
- [-] Enticing "connect"
  - [-] Faker avatars flip in background (https://github.com/Marak/faker.js)
  - [-] Fake avatars continuously changing
  - [-] Dark, centered overlay with zenOSmosis logo extending bottom
- [-] Add user-configurable meeting topic in header
- [-] Share payment badges in a room (i.e. PayPal donate / Stripe pay, etc.)
- [-] Gold effect for logo:  https://www.youtube.com/watch?v=B1O0fQQJ2IY
- [partially-complete] Re-enable farmhash (macOS errors with: farmhash.node: invalid ELF header). IMPORTANT: npm modules for the backend need to be installed on the respective OS.
  - [-] All Dockerfiles should contain "npm install --production"
  - [-] Make a development script to handle dependency install on setup
  - [-] Include Node.js package.json config in root directory to set up child packages in development environments
- [partially-complete] Add UI control for screen sharing
  - [-] Clean up isScreenSharing handling
  - [-] Add audio support (where available)
- [in-progress] TTS Speech synthesis (Google 1 - 4 million characters per month for free) (zenrtc-tts [private] dashboard: https://console.cloud.google.com/apis/api/texttospeech.googleapis.com/overview?folder=&project=mesmerizing-app-292113&supportedpurview=project)
  - [done] Howler audio built into Phantom Server
- [partially-complete] Add HowlerAudio startup sound
  - [-] Add multi-channel Howler (MediaStream via iFrame on server?)
  - [-] "A human / machine participant with X capabilities has joined / left the call / line / party, etc."
  - [done] Connect tone
- [-] Integrate sdp-transform in order to control bitrate (https://www.npmjs.com/package/sdp-transform)
- [partially-complete] Fix black screen on ZenRTC disconnect
- [partially-complete] Show loader when connecting to WebRTC
- [-] Integrate local media audio / video streaming
  - [-] Add consistent player styling (https://videojs.com/getting-started/#install-via-npm)
  - [-] Integrate drag-n-drop
  - [-] Apply stereo audio
- [-] Implement re-settable zenRTCPeer in useZenRTCPeer
- [partially-complete] Share desktop functionality
- [-] Capture device rotation / map to 3D plane
- [-] Fix hot-module-reload functionality between headless Chrome and controller
- [-] 3D text: https://bennettfeely.com/ztext
- [-] Show warning for iOS users w/ version 12 and less (iOS 12 and less cannot receive more than one media stream track of the same type)
- [-] Improve A/V React component implementation
  - [-] Add console logging for playing / paused / stopped status to monitor w/ iOS
- [-] Speech transcription
- [-] Map MIDI to musical notes (https://en.scratch-wiki.info/wiki/MIDI_Notes)
- [deferred] Event after all sounds have loaded
- [-] Client version check
- [partially-complete] alt video dl => stream (yt / etc.)
- [on-hold] jsnes: https://github.com/bfirsh/jsnes (Experiment)
  - [done] jsnes ZenRTC participant (no audio / video in, only data for keystrokes / ROM)
  - [-] AudioContext.createMediaStreamDestination(): https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaStreamDestination
  - [done] Remote bind keyboard controls
  - [done] Enable ROM upload (.nes extension drag and drop?)
- [-] Local/Remote ZenRTCPeer? [edit: Probably not; rename to ZenRTCConnection and have peers within that connection]
- [-] Documentation: Show Puppeteer / Chrome MCU Topology / Flowchart w/ Session Controller / Backend Bridge / distinction between zenRTCPeer and PhantomPeer (zenRTC is the network / "Phantom" is the session)
- [-] Fix error: chrome_session_controller_1 | [0](node:79) UnhandledPromiseRejectionWarning: Error: Protocol error (Runtime.callFunctionOn): Session closed. Most likely the page has been closed.
- [-] Use Gravatar images for user icons?
- [-] (not sure) Force participant to disconnect in WebRTC once socket connection ends?
- [-] Add something like Dr. Sbaitso (https://github.com/danreeves/sbaitso)
  - [-] TTS onEnd event sent to all participants
  - [-] Pull phrases from dictionary, perhaps (https://github.com/danreeves/sbaitso/blob/master/strings.json)
- [done] Add layout panel flip-ins
- [done] Force headless Chrome session to end when all participants have left
- [done] Move TURN server to voice.zenosmosis.com
- [done] Change "experiments" trigger implementation
- [done] Stop local media streams on disconnect / clear SimplePeer
- [done] Implement Phantom disconnect if socket disconnects
  - [done] Ensure underlying Chrome session is removed
- [done] Fix ChromePhantomSession MaxListenersExceededWarning
- [done] Add connection timer
- [done] Rename all reSocketId to socketIoId
- [done] (Initial ChromePhantomSession) Create WebRTCMessageBroker (or something), extending IPCMessageBroker. Use it for enabling multiple peers to talk to one another in the Chrome server
- [done] Connect WebRTC from client to server
- [done] Fix audio issues
- [done] Fix bi-directional streaming
- [done] Fix issue where Safari won't connect if existing Chrome screenshare is running
- [done] Replace public/logo* with speaker.app logo