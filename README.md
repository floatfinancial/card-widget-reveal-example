# Float card reveal example

A single HTML page that shows a USD Float card's details with the [Synctera Reveal Card widget](https://docs.synctera.com/v2/docs/card-widgets-reveal).

The page calls Float's `GET /v1/cards/{card_id}/widget_token/` endpoint, then passes the returned token to the widget. Tokens expire after 5 minutes.

## Requirements

- A Float API token with read access to cards
- The ID of a USD card

## Run it

The widget doesn't work when the page is opened straight from disk (`file://`). Serve it over HTTP instead:

```bash
python3 -m http.server 8080
```

Open http://localhost:8080/widget_token_test.html, enter your API token and card ID, then click **Get token & reveal**.

## Using this in production

This page is for testing only. It sends your API token from the browser. In your own app, request the widget token from your backend and pass only the widget token to the page.

See the [Float API docs](https://docs.floatfinancial.com) for more.