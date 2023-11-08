---
title: incubator-answer
date: 2023-10-28T12:17:54+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1695049761557-cb56d348c297?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTg0NjY0ODB8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1695049761557-cb56d348c297?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTg0NjY0ODB8&ixlib=rb-4.0.3
---

# [apache/incubator-answer](https://github.com/apache/incubator-answer)

<a href="https://answer.dev">
    <img alt="logo" src="docs/img/logo.svg" height="99px">
</a>

# Answer - Build Q&A platform

A Q&A platform software for teams at any scales. Whether it’s a community forum, help center, or knowledge management platform, you can always count on Answer.

To learn more about the project, visit [answer.dev](https://answer.dev).

[![LICENSE](https://img.shields.io/github/license/answerdev/answer)](https://github.com/answerdev/answer/blob/main/LICENSE)
[![Language](https://img.shields.io/badge/language-go-blue.svg)](https://golang.org/)
[![Language](https://img.shields.io/badge/language-react-blue.svg)](https://reactjs.org/)
[![Go Report Card](https://goreportcard.com/badge/github.com/answerdev/answer)](https://goreportcard.com/report/github.com/answerdev/answer)
[![Discord](https://img.shields.io/badge/discord-chat-5865f2?logo=discord&logoColor=f5f5f5)](https://discord.gg/Jm7Y4cbUej)

## Screenshots

![screenshot](docs/img/screenshot.png)

## Quick start

### Running with docker

```bash
docker run -d -p 9080:80 -v answer-data:/data --name answer answerdev/answer:latest
```

For more information, see [Installation](https://answer.dev/docs/installation)

### Plugins

Answer provides a plugin system for developers to create custom plugins and expand Answer’s features. You can find the [plugin documentation here](https://answer.dev/docs/development/extending/).

We value your feedback and suggestions to improve our documentation. If you have any comments or questions, please feel free to contact us. We’re excited to see what you can create using our plugin system!

You can also check out the [plugins here](https://github.com/answerdev/plugins).


## Contributing

Contributions are always welcome!

See [CONTRIBUTING](https://answer.dev/docs/development/contributing/) for ways to get started.

## License

[Apache License 2.0](https://github.com/answerdev/answer/blob/main/LICENSE)