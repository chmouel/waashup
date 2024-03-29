# waashup

Keep your tekton task and pipleine images updated

## Description

waashup is a simple shell script, checking if your image in your tekton tasks
that has a sha256 is kept updated. 

It uses skopeo to inspect the remote registry for a new Digest.

It will try to optimize and only fetch once.

It output it in a simple make format with : 

```
file:LINE: message
```

so you can plug this in your EDITOR or anything that understand that format

## Screenshot

<img width="1394" alt="image" src="https://user-images.githubusercontent.com/98980/214255139-4585618c-7516-477c-b379-f5b6712233f7.png">

## Installation

Copy the [shell script](./washuup) somewhere

### Requirements

- Bash4
- [Skopeo](https://github.com/containers/skopeo/)

## Usage

You simply need to pass the yaml files as argument.

It will try to detect for linux/amd64 platforms by default. 
If you want another platform/os you can set the env variable  `TARGET_OS`
`TARGET_ARCH` or set the `-o` (for a `TARGET_OS`) or `-a` (for a `TARGET_ARCH`)
to redefine them.

It will only print the images that are not up to date. Unless you use the
option `-i` and it will do the replacement in place.

## TODO

- Use python-yaml to go to avoid shell quoting issues and better image detection
- Handle tags?

## BUGS

- may be buggy with some characters due of shell quoting issues.

## Copyright

[Apache-2.0](./LICENSE)

## Authors

Chmouel Boudjnah

- Fediverse - <[@chmouel@chmouel.com](https://fosstodon.org/@chmouel)>
- Twitter - <[@chmouel](https://twitter.com/chmouel)>
- Blog  - <[https://blog.chmouel.com](https://blog.chmouel.com)>
