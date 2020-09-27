# Open Grant Proposal: Hymn Sheet - Hack to MVP

**Name of Project:** Hymn Sheet

**Proposal Category:** app-dev

**Proposer:** philholden

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

_Please consider this for an IPFS grant if not applicable to FileCoin._

Normally Churches worship using a projector for lyrics. With lock down they are not able to sing indoors. Hymn Sheet enables a large number of people to sing socially distanced outdoors by seeing lyrics at the same time on their mobile phones. One phone acts as a controller controlling what all other phones see. It also works with projectors, tablets smart TVs and laptops. See the Hack FS presentation here:

https://youtu.be/nR2-zuYPRs4

I wish to extend Hymn Sheet by adding other shared user experiences:

- Slide shows
- Quotes
- Images
- Audio
- Video
- IFrame

In addition to this I would like to streamline the user journey and improve the UX.

## Value

Demonstrate that IPFS PubSub is ready to make real time shared user experiences. With Covid many more people are working remotely. Tools we use to collaborate and educate (Teams, Slack and Zoom) are crude and generic. Building a rich domain specific shared user experience will show people what is possible in other domains.

## Risks

The biggest risks are:

1. Not finding an initial group of users
2. Friction

Launching multi-user experiences is hard because it is not enough to have a large number of people excited by a project. They have to discover each other and organize themselves to be using it at the same time.

This app needs to get its R above 1.0. The rewards of getting it right are huge because growth happens in groups not individuals.

## Deliverables

### Improved user experience

HackFS demonstrated the vision of HymnSheet. The response from the tech community has been very positive. However being a hackathon there are many things in the user experience that need to be smoothed out.

### Integrate additional viewers

Viewer components in Hymn Sheet attempt to use screen space and resolution as effectively as possible. They also respond to browser resizes, dragging between windows of different resolution and device orientation changes.

In HymnSheet we release these viewers as independent npm modules so others can use them in their apps.

During the Apollo Hackathon I have been working on:

- **[Slide show viewer:](https://www.npmjs.com/package/@omysoul/svelte-pdf-viewer)** PowerPoints can be exported as PDFs. Mozilla has a JS PDF viewer this can be wrapped to make a presentation viewer. The controller would control which slide is viewed on all connected devices.
- **[Quote viewer:](https://www.npmjs.com/package/@omysoul/svelte-quote-fit)** The quote viewer shows a passage of text with good typography zoomed to be fill the screen. It allows limited formatting.

These viewer components have been developed outside of HymnSheet and need to be integrated into it. This incudes making these types of media controllable. This means creating custom controller components for each media type.

### Create additional viewers

I would like to create additional viewers for other types of media:

- **Image:** View image full screen with contain and cover options.
- **Audio:** People wearing headphones hear the same audio at the same time (synced to within about 1 second). The sync will not be good enough for use without headphones (for future plans see [Sub 20 Millisecond Audio Sync](https://github.com/philholden/hymnsheet/issues/17)).
- **Video:** People wear head phones and see video clip at roughly the same time.
- **IFrame viewer:** Loads an IFrame and can forward channel PubSub messages to the IFrame using postMessage. This will allow users to implement custom viewers (E.g. three.js, d3.js).

# Switchable viewers

Currently Hymn Sheet only has one type of viewer. To have these other kinds of viewers work I will need to make views switchable based on a `contentType` in the PubSub message.

## Development Roadmap

### October 31st

- Integrate PDF viewer and quote viewer into Hymn Sheet app
- Make viewers switch based on contentType of PubSub message
- Release any updates to these viewers to npm
- Add APACHE2 licence
- Create controller components for PDFs and Quotes so it is possible to broadcast quotes and slides

People required: 1
Funding requested: \$3000

### November 30th

The aim is to have Hymn Sheet ready for mass usage in December. So getting the UX as slick as possible will be the aim for this month.

- Better user journey
- Respond to user testing
- Improve performance
- Fixed headers, make Hymn Sheet launch from native QR scanners etc. many small fixes like these are needed.
- SetList component: A controller that allows songs, quotes and slides mixed together. These elements can be interspersed with speaker notes.
- UI for creating set lists might be rudimentary at this stage.

People required: 1
Funding requested: \$3000

### December 31th

- Create viewer components for image, video and audio
- Create IFrame viewer
- Release these on npm as APACHE2 MIT
- Integrate into Hymn Sheet viewer
- Create controller components for these media types
- Improve tool for authoring SetLists

People required: 1
funding requested: \$3000

## Total Budget Requested

\$9000

## Maintenance and Upgrade Plans

I will continue to maintain and build upon HymnSheet with others welcome to contribute.

These are some planned future features:

- Hymn Sheet viewer in an IFrame. This will allow others apps to display a HymnSheet viewer as an embed. It would allow users of other Web 3 apps to play live slide shows etc to their users.
- Allow other apps to integrate Hymn Sheet controller functionality and messaging functionality. E.g. clicking on a verse in a Bible app would display that verse to channel subscribers using the svelte-quote-fit viewer.
- Sub 20ms clock sync. Having clocks synced close enough to play audio without headphones opens up many interesting use cases.
- Slim down Hymn Sheet. Hymn Sheet mainly uses IPFS PubSub. However this is probably a tiny part of the bundle (currently over 2M). I think we could get this down to 10% if we switched to LibP2P or just gossip-sub
- Bring your own data. The data used for Hymn Sheet PDFs, song books, video are applicable to many other application. It would be great if Hymn Sheet integrated with a rich IPFS file explorer.
- Having something at the protocol level for building Hymn Sheet / Firebase style apps. This is where you want to get the current value of something (without syncing all previous state like OrbitDB does). Hymn Sheet bases its data model on video compression where I-frames hold all information needed to render a frame and P-frames are some kind of a delta on the previous frame. When a new user syncs they should get the latest I-frame and all subsequent P-frames.

# Team

## Team Members

- Phil Holden

## Team Member LinkedIn Profiles

- Phil Holden [LinkedIn profile](https://www.linkedin.com/in/phil-holden-5155bb13b/)

## Team Website

- https://hymnsheet.xyz/
- https://hymnsheet.substack.com/

## Relevant Experience

I have many years experience working as a UI developer. I have developed three component libraries. I am an egghead.io instructor.

## Team code repositories

- [Hymn Sheet](https://github.com/philholden/hymnsheet)
- [@omysoul/svelte-song-display](https://github.com/philholden/svelte-song-display)
- [@omysoul/svelte-quote-fit](https://github.com/philholden/svelte-quote-fit)
- [@omysoul/svelte-pdf-viewer](https://www.npmjs.com/package/@omysoul/svelte-pdf-viewer)

# Additional Information

I will be submitting proposals to speak about Hymn Sheet to online dev conferences. I will also see if I can get on some JS podcasts. I would use these opportunities to raise awareness of IPFS and LibP2P.
