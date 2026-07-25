<!--
SPDX-FileCopyrightText: 2026 TheBananaPancake <did:plc:3ywraszv5eqhnlvzumwju5fa>
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Contribution guide

This website is built with [Vite](https://vite.dev). First, clone into the
repository and install dependencies with:
```sh
npm install
```
make your changes and test them by hosting the website on `localhost:5173`
by running:
```sh
npm run dev
```
and re-compile the Svelte code,
```sh
npm run build
```

If you find an error, please either make an issue or a pull request. Please
make commits using:
```sh
git commit -s"
```
Please use `-s` to add a signed-off-by line to show that you own the rights
to the code in your commit. The command appends a line onto the end of the
commit message with your name and email address, which you configure with
Git. To do this, use
```sh
git config user.name "Your new name!"
```
and
```sh
git config user.email "youremail@example.com"
```
> [!TIP]
> If you're on Tangled and do not wish to use your real email address due to privacy 
> concerns, you can set your email to your DID (Decentralised Identifier). You can find
> this in your Tangled user settings!

If you haven't added a signed-off-by line, you can edit your commit using:
```sh
git commit --amend -s
```
This will open your configured editor to edit the commit message. Use the
following template to do so:

```
LANGUAGE(S): short description of change

Optional longer description if necessary.

Signed-off-by: user <email>
```

For any other information, please refer to the [Svelte documentation](https://svelte.dev/docs)
and the [Vite guide](https://vite.dev/guide/).
