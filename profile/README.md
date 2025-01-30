# Welcome

**Everything here is very much a work in process but in general,**

The aim is to build better iOS & macOS rich text views—using native text rendering technologies—that overcome the limitations of platform specific text views and that are easily embeddable in your app. 

## Marketing Abstract

Nowadays it’s not so easy to become an App Store millionaire when apps are a dime a dozen and especially when native UI frameworks have been losing their competitive edge with regard to web technologies (which is a shame in and of itself).   

The overarching goal of the SuperSwiftMarkup libraries is to deliver the next generation of text views that support user experiences unparalleled by web technologies. So that you can squeeze out that extra competitive edge in this hyper saturated and globalized marketplace of software.

(Luckily iOS users have been known to be especially picky when it comes to text functionality. Just ask the Flutter team.) 

## Rationale

When it comes to supporting markdown is your app, platform specific native text views only support a limited subset of markdown. Which is generally limited to just basic inline formatting within paragraph blocks and nothing more.
 
As far as supporting the full range of e.g. the GitHub Flavored Markdown Spec, not only are you out-of-luck but there is little to no support at the level of basic building blocks. Technically TextKit has a concept of “text tables”, but it’s limited to just AppKit with no support for iOS. 

In general **developers are left to their own devices** and while there are many preexisting markdown rendering libraries, none so far are satisfactory.

Also with regard to “developers are left to their own devices”, you yourself are a *do-it-yourself* kinda person. Technically, building a markdown preview in terms of SwiftUI views is super easy, but the tradeoff here is no text selection across distinct text views. Likewise, building a markdown preview via an embedded web view is also super easy but the tradeoff here is that web views are themselves black boxes that don't integrate well with the native UI system. E.g. when nested in complex view trees, web views will break layout, and if you need to extend the default text selection behavior to support app specific behavioral requirements, IMO such is a problem that no web app has yet to solve. So technically there are solutions, but none—so far—are satisfactory, and furthermore **if you also need to support edit-ability:** good luck.      


## Organization Timeline

### [SuperSwiftMarkdownPrototype]( https://github.com/SuperSwiftMarkup/SuperSwiftMarkdownPrototype )

Initially the work began with a *proof-of-concept* prototype with the following aims: 
- Implement a native text renderer that supports all block types as defined in the GitHub Flavored Markdown Spec.
- With uniform behavior concerning text selection and selection-based navigation. Including: 
    - This includes the ability to select any inline text within any markdown block and be able to extend that selection across multiple and varying markdown block types. 
    - Cross platform support for multiple cursors / selections. 
- Implement all of the above without relying on macOS only APIs.
    - While the prototype was implemented in terms of AppKit APIs, the port to iOS should be relatively trivial. Especially since this project was itself based on an earlier codebase that was implemented in terms of UIKit and I have verified that the TextKit 2 functionality concerning text selections does indeed work on—at least—iOS 17 (which I honestly thought would be too good to be true lol). 

### [SuperSwiftMarkup]( https://github.com/SuperSwiftMarkup/SuperSwiftMarkup )

**At the time of this writing:**

Now that the core functionality has been proven viable, I (the author) have learned much and I intend to translate my experience and lessons learned from the *proof-of-concept* prototype codebase into a viable set of libraries that app developers can depend upon. Starting from a blank slate.

So keep in mind:
- This project is a complete rewrite from the ground up.
- The git tree is also a fresh start.
- At the time of this writing this project is in heavy development and does not yet present any cool tangible functionality.
- So head over to the aforementioned [*proof-of-concept* prototype](https://github.com/SuperSwiftMarkup/SuperSwiftMarkdownPrototype) to see the past history and screenshots from where that project left off (spoiler alert it’s super cool). 
- For the layperson, unless you’re interested in contributing towards or influencing the initial evolution of the SuperSwiftMarkup libraries, **please check back** every so often to see when some libraries therein are ready for real world use. 
- But if you’re interested in influencing the initial evolution of this project, then by all means dive in. 🙂


**High Level Objectives:**
- First class (cross platform) support for all markdown block types, with uniform behavior concerning text selection and selection-based navigation.
- First class (cross platform) support for multiple cursors/selections.
- Default support for everything under "Meeting the expectations of iOS and macOS users" (see [Appendix](#Appendix)).

**Additionally:**
- Where the rendering engine is designed in such a way that can accommodate,
    - Horizontally scrollable fragments (on a per-fragment basis) as an alternative to text wrapping. Which is particularly desirable for e.g. long tables that cannot neatly fit within their available view space.

## Conclusion

**Overall I hope you’re excited as I am!** 

Personally I, the author (Colbyn Wadman), have been messing around with miscellaneous problems concerning text processing and text rendering (in one form or another) for a very long time and—as far as the POC has demonstrated—it’s good to see something interesting come from it, and when I release my work, I hope you’ll be pleased with the results. 🤞

## Links

### Author’s Developer Blogs 

- [Medium]( https://medium.com/@colbyn )
- [SubStack]( https://substack.com/@colbynwadman )
