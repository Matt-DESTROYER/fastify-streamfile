[![Version](https://img.shields.io/npm/v/fastify-streamfile.svg?style=flat)](https://www.npmjs.com/package/fastify-streamfile)
[![Install size](https://packagephobia.com/badge?p=fastify-streamfile)](https://www.npmjs.com/package/fastify-streamfile)
[![Minzipped size](https://img.shields.io/bundlephobia/minzip/fastify-streamfile?style=flat)](https://www.npmjs.com/package/fastify-streamfile)
[![Downloads/month](https://img.shields.io/npm/dm/fastify-streamfile.svg?style=flat)](https://www.npmjs.com/package/fastify-streamfile)

# fastify-streamfile
A lightweight package that adds essential, easy-to-use file sending functionality using decorators.

## Using fastify-streamfile
```js
import FastifyStreamFile from "fastify-streamfile";

fastify.register(FastifyStreamFile);
```

## Methods
These are methods exported to the `reply` object.

---

```js
reply.streamFile(String file);
reply.streamFile(String file, String root);
```
Sends a file using the input filename (`file`) and located in the current working directory, or optionaly via the `root`, as the response, also setting the appropriate `type` using the file's extension.

---

```js
reply.sendFile(String file);
reply.sendFile(String file, String root);
reply.sendFile(String file, function callback);
reply.sendFile(String file, String root, function callback);
```
Sends a file using the input filename (`file`) and located in the current working directory, or optionally via the `root`, as the response, also setting the appropriate `type` using the file's extension. You can also manipulate the file's content using an optional `callback`.

---

These are methods exported to the `fastify` object.

---

```js
fastify.static(String folder);
fastify.static(String folder, String root);
fastify.static(String folder, String root, String route);
fastify.static(String folder, String root, String route, Integer depth)
```
Hosts all files in the input folder (`folder`) at the input route (`route`), recursing through folders to an input depth (`depth`, which defaults to `10`).
