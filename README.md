# scale-fetch-test

A single static page that checks whether a tablet's browser can read a weight from a scale on a local network.

It makes the same GET request a web application would (`/scale.cgi?scale=N`) and reports:

- PASS: the browser read the weight
- Reached but blocked by CORS
- Blocked or unreachable (most likely the browser's mixed-content block when this HTTPS page calls a plain HTTP address)
- No answer (scale not reachable)

It stores nothing and sends nothing anywhere. The tester can copy the results, or tap an email button that opens their own mail app with the results filled in.

## Link parameters

Add these to the page address to pre-fill it:

- `ip` - scale address, e.g. `ip=192.168.1.50`
- `n` - scale number, default 1
- `https` - a full HTTPS URL for an optional second test
- `to` - address for the Email results button (kept out of the repo on purpose)

Example: `https://scalemangdw.github.io/scale-fetch-test/?ip=192.168.1.50&to=you@example.com`

## Using it

1. On a device on the same network as the scale, open the page.
2. Step 1: open the scale directly. You should see the JSON weight. If not, fix the network first.
3. Step 2: tap Run test.
4. Send the results back.

`sample.json` is a stand-in for a scale reply, so the HTTPS test can be tried against this same site.
