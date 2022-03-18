# PolyEcho

PolyEcho is a schelling game where the objective is to publicly co-create songs worthy of purchase by NFT collectors.

**LIVE DEMO**: <https://polyecho.xyz>

---

## Getting Started

There is some local setup that needs to happen to fully run this client application locally.

Dependencies:

- npm or yarn
- Node.js
- MongoDB

### 1. Install dependencies

First install the dependencides needed. You can download the latest version of Node.js [here](https://nodejs.org/en/download/).  You can check that you are running NPM and Node with the following commands:

```bash
node -v
# v16.14.0

npm -v
# 8.3.1
```

Install the client dependencies with the following command:

```bash
yarn install
# or
npm install
```

### 2. Environment Variables

Next, set up local environment variables by copying over the sample env. Run the following command:

```bash
# unix
cp sample.env .env.local
# windows
xcopy sample.env .env.local
```

**NOTE:** Please reach out to the core team for a set of values to fill in your local env file.

### 3. Run the Application

Finally, you can run the development server using the following command:

```bash
yarn dev
# or
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

---

## Setting Up A Local Database (MongoDB)

This client application is using the built-in Next.js API routes that read and write to a local Mongo database. Here are our recommended steps for getting up and running with a local MongoDB environemnt:

### 1. Install a MongoDB Host

This will set up a host to run in the background on the machine. You can then connect to it via a number of methods when it is up.

- For Mac users, you can follow the steps listed [here](https://medium.com/macoclock/setup-mongodb-on-macos-94e0c687c649).
- For Windows users, you can follow the steps listed [here](https://medium.com/stackfame/run-mongodb-as-a-service-in-windows-b0acd3a4b712).

### 2. Install a MongoDB Client

There are many ways to interact with a MongoDB host. My recommendation is to use a GUI, as it makes for viewing the data easily, and MongoDB Compass is free and easy to use. Install it using the documentation [here](https://docs.mongodb.com/compass/current/install/).

### 3. Create a Connection

Once MongoDB Compass is installed and you have a MongoDB host running in the background, you can now connect the client to the host and set up this new connection. Open up Compass and click "New Connection" in the top left of the GUI, or in the menubar. Paste in the local connection string; it should look similar to this on Mac:

`mongodb://localhost:27017/?readPreference=primary&appname=MongoDB%20Compass&ssl=false`

### 4. Create a Database and Link It

Create a new database for polyecho. Title it `polyecho` or whatever suits your fancy. It may prompt you to add a collection to it as well.  Please add a `users` collection.

The important bit is to **update your local environment variables** in the client app. Update the following in `.env.local` to your new connection string:

`MONGODB_URI=mongodb://localhost/polyecho`

This may look different for windows users, but this will now allow the client app to work with a local database.

---

## Issues

We encourage the open-source atmosphere. If you find any bugs or issues with this repository, don't hesitate to [file an issue](https://github.com/polyecho/polyecho/issues/new) for it. We will work to continually engage with these issues and encourage you to contribute.
