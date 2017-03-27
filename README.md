# Project 7 - WordPress Pentesting

Time spent: 10 hours spent in total

> Objective: Find, analyze, recreate, and document up to **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. Authenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: Authenticated Cross-Site Scripting (XSS) in post/page (text editor mode). Editor user and up.
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough:
  - [ ] Steps to recreate: Code was entered into a new post using the HTML edit mode.
        ...
        <a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>
        ...
  - [ ] Affected source code:
    - [Link 1](https://klikki.fi/adv/wordpress3.html)
1. Authenticated Shortcode Tags Cross-Site Scripting (XSS)
  - [ ] Summary: A payload was placed in a page or post to create an XSS pop up
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 4.2.5
  - [ ] GIF Walkthrough:
  - [ ] Steps to recreate: The following was added to a post's content and created an XSS pop up when on mouse over:
  ...
        TEST!!!<figure style="width: 1px;" class="wp-caption alignnone"><figcaption class="wp-caption-text"><a href="</figcaption></figure></a><a href="http://onMouseOver='alert(1)'">Click me</a></p>"
        ...
  - [ ] Affected source code:
    - [Link 1](http://blog.checkpoint.com/2015/09/15/finding-vulnerabilities-in-core-wordpress-a-bug-hunters-trilogy-part-iii-ultimatum/)
1. Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [ ] Summary: A simple XSS script is added into a URL in order to bypass the shortcode parser.
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 4.2.13
  - [ ] GIF Walkthrough:
  - [ ] Steps to recreate: Creating a new post with the following youtube link creates an XSS message:
        ...
        https://youtube[.]com/watch?v=abc<svg onload=alert(1)>"
        ...
  - [ ] Affected source code:
    - [Link 1](https://blog.sucuri.net/2017/03/stored-xss-in-wordpress-core.html)

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work
    One challenge required the use of an MacOS or Linux operating system. Also, the majority of the vulnerabilities provided very little information on how they could be recreated.

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
