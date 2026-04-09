# Matrix Widget Demo

Bare-bones Matrix widget prototype with two buttons.

## Files

- `index.html` — widget page

## What it does

- Tries to initialize the Matrix widget API
- Shows two buttons:
  - `Approve`
  - `Details`
- On click, tries to send plain room messages:
  - `approve`
  - `details`
- Includes a visible status/log area for debugging

## Important

This is still prototype-grade and intentionally ugly.
It is meant to answer one question only:

> Can a hosted widget in Element behave like simple quick-reply chips?

## Serve locally

```bash
cd /home/wunnle/.openclaw/workspace/matrix-widget-demo
python3 -m http.server 8787
```

Then open:

```text
http://localhost:8787
```

In a plain browser tab, the widget API will probably fail to initialize. That is expected.

## Real test requirements

To test it as an actual widget, you need:

1. HTTPS hosting for this page
2. A Matrix room where you can add a widget
3. Element client support for widgets/capabilities

## Expected behavior

- In normal browser:
  - UI loads
  - status/log will say widget API init failed
- In widget-capable Matrix client:
  - widget should try to initialize
  - button taps should attempt to send `approve` / `details` into the room

## Next likely fixes

Depending on client behavior, we may need to adjust:

- capability requests
- widget startup handshake
- SDK import source/bundling
- message sending method
- room-scoped permissions
