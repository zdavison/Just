#   Just: Swift HTTP for Humans [![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)

<img src="https://raw.githubusercontent.com/JustHTTP/Just/master/Docs/IconMasked.png" width="280" height="280">

Just is a client-side HTTP library inspired by [python-requests][] - HTTP for Humans.

Swift 2.0 support can be found on *[swift-2.0][]* branch.

*Follow [@JustHTTP][twitter] for updates, if you are into that kind of things* 😉

[python-requests]: http://python-requests.org "python-requests"
[twitter]: https://twitter.com/JustHTTP
[swift-2.0]: https://github.com/JustHTTP/Just/tree/swift-2.0 "Just support for Swift 2.0"
#   Features

Just lets you to the following effortlessly:

-   URL queries
-   custom headers
-   form (`x-www-form-encoded`) / JSON HTTP body
-   redirect control
-   multpart file upload along with form values.
-   basic/digest authentication
-   cookies
-   timeouts
-   synchrounous / asyncrounous requests
-   upload / download progress tracking for asynchronous requests
-   friendly accessible results

#  Use

The simplest request with Just looks like this:

```swift
//  A simple get request
Just.get("http://httpbib.org/get")
```

The next example shows how to upload a file along with some data:

```swift
//  talk to registration end point
let r = Just.post(
    "http://justiceleauge.org/member/register",
    data: ["username": "barryallen", "password":"ReverseF1ashSucks"],
    files: ["profile_photo": .URL(fileURLWithPath:"flash.jpeg", nil)]
)

if (r.ok) { /* success! */ }
```

Here's the same example done asyncronously:

```swift
//  talk to registration end point
Just.post(
    "http://justiceleauge.org/member/register",
    data: ["username": "barryallen", "password":"ReverseF1ashSucks"],
    files: ["profile_photo": .URL(fileURLWithPath:"flash.jpeg", nil)]
) { (r)
    if (r.ok) { /* success! */ }
}

```

Just can do much, much more.
Read *Getting Started* [on the web][starting link] or
[in this playground][starting playground] to learn more!

[starting playground]: https://raw.githubusercontent.com/JustHTTP/Just/master/Docs/QuickStart.zip
[starting link]: http://docs.justhttp.net/QuickStart.html

#  Install

Here are some ways to leverage Just.

## Carthage (recommended)

Include the following in your Cartfile:

    github "JustHTTP/Just"

Just includes dynamic framework targets for both iOS and OS X.

## Manual

Drop `Just.xcodeproj` into your project navigator. Under the *General* tab of
your project settings, use the plus sign to add `Just.framework` to
*Linked Framework and Libraries*. Make sure to include the correct version
for your target's platform.

It's also common to add Just as a git submodule to your projects repository:

    cd path/to/your/project
    git add submodule add https://github.org/JustHTTP/Just.git


## Source File

Put `Just.swift` directly into your project. Alternately, put it in the
*Sources* folder of a playground. (The latter makes a fun way to explore the
web.)


[Carthage]: https://github.com/Carthage/Carthage "Carthage"


#  Contribute

Pull requests are welcome. Here are some tips for code contributors:

[Carthage][] is needed to install [Quick][], before you can run the tests.
For Xcode rebels, checkout `Makefile` (you'll need [xcpretty][]).

HTML documentation pages are generated by literate programmin tool [docco][]


[Quick]: https://github.com/Quick/Quick "Quick"
[xcpretty]: https://github.com/supermarin/xcpretty "xcpretty"
[docco]: http://jashkenas.github.io/docco/ "docco"

#  License

MIT, see [LICENSE.md](https://github.com/JustHTTP/Just/blob/master/LICENSE.md).
