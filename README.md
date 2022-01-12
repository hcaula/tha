# Take Home Assignment

The central repository for the Take Home projects repository for the Origin assignment.

## Overview

This application can calculate an user's financial health wellness based on their annual income and monthly costs. This score is assessed by three values: "low", "medium" and "healthy".

It's a [client-side rendered application](https://github.com/hcaula/tha-client), written in React, that communicates with a [Node.js server](https://github.com/hcaula/tha-server).

## Developing

### Requirements

- [Node](https://nodejs.org/en/download/) version 16.13 or higher (we recommend using [NVM](https://github.com/nvm-sh/nvm) for installing and managing Node versions);
- [Yarn](https://classic.yarnpkg.com/lang/en/docs/install/).

### Quick start

1. Clone and update the git submodule repositories:

```sh
git submodule update --init --recursive --remote --merge
```

2. Go the the server repository and install its dependencies:

```sh
cd ./tha-server
yarn install
```

3. Run the server:

```sh
yarn start
```

The server should be running locally and accessible at http://localhost:3002.

4. Go the the client repository and install its dependencies:

```sh
cd ../tha-client # Assuming you are inside the server repository
yarn install
```

5. Run the client:

```sh
yarn start
```

The client should be running locally and accessible at http://localhost:3000.

## General technical decisions

### Why is this application client-side rendered instead of server-side?

One major advantage to go for a server side rendered approach is that it would be possible for search engines such as Google to index the page and show it in their search results. However, given that the nature of this demo app is to be very user input centered, fetch JSON data from servers and eventually have authentication implemented, it would be more flexible to develop it using client side rendered frameworks, such as **create-react-app**.

### JavaScript vs TypeScript

While I still believe JavaScript is better suited for web application where the developer has full control of the data flow, I have to surrender to **TypeScript**. It has been vastly adopted by the community, support seems to be migrating to it and it's very robust. I wouldn't be surprised if such approach would be copied to other non strongly typed languages such as Ruby and Python.

### REST vs GraphQL

GraphQL is a great option for applications like this. It provides an easy documentation that servers as a "strong protocol" for both the frontend and backend applications, which allows a more easily development, since both of them knows exactly what to expect. However, since this application should only contain one route, for simplicity's sake, it's better to go for **REST**. It's probably quicker to implement on both sides.

### How to test these applications?

An option that came to my mind was abuse the fact that this demo app has basically one functionality and run full end-to-end tests on it, with automated tests running the web application that is connected to the server application. We probably could achieve near 100% coverage very quickly. However, this would not be sustainable for a very long time in case this application grew, since the overhead to run these tests would be rather large. So, if this application happened in a "real life scenario", it would be more realistic to test the applications separately.

But, we still want to write few, but great tests. So, the best scenario is to write integration tests for both of them.

## What's next?

- Play around with the project, trying different values and seeing how it works;
- Learn more details about the [client](https://github.com/hcaula/tha-client) and [server](https://github.com/hcaula/tha-server) projects.
