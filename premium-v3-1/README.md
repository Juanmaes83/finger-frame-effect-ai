# Portal Studio V3.1 — Unified Lucy AI

V3.1 removes the V3 iframe + floating AI dock architecture. Portal Studio and Lucy now share one DOM, one canvas and one control panel.

## UI

The right panel has three tabs:

- PORTAL — camera/video source, portal content, diagnostics, look and gesture behaviour.
- AI LIVE — Lucy connection, source mode, style/prompt and connection diagnostics.
- OUTPUT — recording and export.

There is no second overlapping panel.

## Lucy flow

1. Start camera in PORTAL.
2. Open AI LIVE.
3. Add a Decart development credential.
4. Connect Lucy.
5. AI and SPLIT remain disabled until a real remote Lucy stream is received.
6. Select ORIGINAL / AI / SPLIT.

The Lucy stream is normalized through a hidden canvas so its orientation matches the mirrored Portal Studio camera. SPLIT uses cover/crop rather than horizontally stretching each full frame.

## Reliability

Diagnostics expose SDK, auth, session, remote video and active output. Remote video track end, SDK errors and disconnect callbacks can trigger reconnect with capped backoff.

## Credential security

For local development/testing, this preview accepts a Decart API credential directly in the browser and can optionally keep it in session/local storage.

Do not use a permanent Decart secret key this way in a production deployment. Decart's current platform guidance is to mint short-lived client tokens server-side for browser/mobile realtime sessions and send only the temporary token to the client. A production version should replace the browser secret-key field with a call to a small token endpoint.

Never commit credentials to GitHub.

## Status

Review build only. Do not merge to main until browser + Lucy runtime validation is complete.