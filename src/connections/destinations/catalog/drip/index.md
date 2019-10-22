---
title: Drip
---
Our Drip destination code is all open-source on GitHub if you want to check it out: [Javascript](https://github.com/segment-integrations/analytics.js-integration-drip),(iOS and Android work via the server destination).

## Getting Started

When you toggle on Drip in Segment, this is what happens:

+ Our CDN is updated within 5-10 minutes. Then our snippet will start asynchronously loading Drip's track.js onto your page. This means you should remove Drip's snippet from your page.
+ Since Drip only records custom events and custom user data, no events or users will appear in Drip until you start using the API outlined below.

## Identify

When you call [`identify`](/docs/spec/identify/) on analytics.js, we call [`identify`](/docs/spec/identify/) on Drip and pass through all of the user traits that were included on that call. You must pass email as a trait to identify the user to Drip. Note that if you want to do cross-domain tracking, after you've enabled it in the Drip UI, you'll need to pass `email` as a trait on the identify call on both domains.

## Track

When you call [`track`](/docs/spec/track/), we'll send the event to Drip with the event `name` and all `properties` that you specified. If you include `revenue` as a property, it will get passed to Drip as the conversion value of this event.

**Note:**
- If you are sending custom server side events, you must include an `email` property of the user that the event belongs to.

- Only conversions that are attributed to a Drip email delivery will show on the conversions dashboard page.

## Sending Data from Drip

Drip supports sending [email events](/docs/spec/email/) to other tools on the Segment platform. These events will be sent as `track` calls to the other destinations you've turned on.

{% include content/integration-foot.md %}