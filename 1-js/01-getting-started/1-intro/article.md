# Lời giới thiệu về JavaScript

Chúng ta hãy cùng tìm hiểu những điều đặc biệt về JavaScript, chúng ta có thể đạt được gì với nó, và những công nghệ có thể hoạt động tốt với nó.

## JavaScript là gì?

_JavaScript_ nguyên bản được tạo ra để "giúp cho các website như được sống".

Chương trình trong ngôn ngữ này được gọi là _scripts_. Chúng có thể được viết ngay trong HTML của trang web và chạy tự động khi trang tải.

Scripts được cung cấp và thực thi như văn bản thuần túy. Chúng không cần được đặc biệt chuẩn bị hoặc biên dịch để chạy.

Khía cạnh này, JavaScript thực sự khác biệt so với ngôn ngữ khác được gọi là [Java](<https://en.wikipedia.org/wiki/Java_(programming_language)>).

```smart header="Tại sao nó gọi là <u>Java</u>Script?"

Khi mà JavaScript được tạo ra, nó ban đầu có một cái tên khác: "LiveScript". Nhưng Java rất phổ biến vào thời điểm đó, vì vậy quyết định việc đặt một ngôn ngữ mới như là "em trai" của Java sẽ giúp ích.

Nhưng khi phát triển, JavaScript đã trở thành một ngôn ngữ hoàn toàn độc lập với một đặc tả riêng gọi là ECMAScript, và hiện nay nó không còn liên quan gì đến Java nữa.
```

Ngày nay, JavaScript chạy không chỉ trên trình duyệt, mà còn trên máy chủ (server), hoặc thực sự trên bất kỳ thiết bị nào có một chương trình đặc biệt được gọi là [bộ máy JavaScript](https://en.wikipedia.org/wiki/JavaScript_engine).

Trình duyệt có nhúng một bộ máy gọi là "máy ảo JavaScript".

Sự khác biệt giữa các bộ máy "codenames". Ví dụ:

- [V8](<https://en.wikipedia.org/wiki/V8_(JavaScript_engine)>) -- trong Chrome, Opera and Edge.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- trong Firefox.
- ...Và còn nhiều "codenames" khác như: "Chakra" cho IE, "JavaScriptCore", "Nitro" và "SquirrelFish" cho Safari, v.v.

Các thuật ngữ trên đây nên nhớ vì chúng được sử dụng trong các bài viết của các nhà phát triển trên internet. Chúng ta cũng sẽ sử dụng chúng. Ví dụ, nếu "một tính năng X được hỗ trợ bởi V8", thì nó có thể hoạt động trên Chrome, Opera và Edge.

```smart header="Bộ máy hoạt động như thế nào?"

Bộ máy JavaScript là phần mềm phức tạp. Nhưng cơ bản thì nó rất đơn giản.

1. Bộ máy (nhúng nếu đó là trình duyệt) đọc ("phân tích cú pháp") script.
2. Sau đó nó chuyển đổi ("biên dịch") script thành mã máy.
3. Và khi mà chương trình chạy, chúng tương đối nhanh.

Bộ máy áp dụng các tối ưu hóa ở mỗi bước của quá trình. Nó thậm chí theo dõi script đã biên dịch khi chạy, phân tích dữ liệu đi qua nó, và tối ưu hóa mã máy dựa trên kiến thức đó.
```

## What can in-browser JavaScript do?

Modern JavaScript is a "safe" programming language. It does not provide low-level access to memory or the CPU, because it was initially created for browsers which do not require it.

JavaScript's capabilities greatly depend on the environment it's running in. For instance, [Node.js](https://wikipedia.org/wiki/Node.js) supports functions that allow JavaScript to read/write arbitrary files, perform network requests, etc.

In-browser JavaScript can do everything related to webpage manipulation, interaction with the user, and the webserver.

For instance, in-browser JavaScript is able to:

- Add new HTML to the page, change the existing content, modify styles.
- React to user actions, run on mouse clicks, pointer movements, key presses.
- Send requests over the network to remote servers, download and upload files (so-called [AJAX](<https://en.wikipedia.org/wiki/Ajax_(programming)>) and [COMET](<https://en.wikipedia.org/wiki/Comet_(programming)>) technologies).
- Get and set cookies, ask questions to the visitor, show messages.
- Remember the data on the client-side ("local storage").

## What CAN'T in-browser JavaScript do?

JavaScript's abilities in the browser are limited to protect the user's safety. The aim is to prevent an evil webpage from accessing private information or harming the user's data.

Examples of such restrictions include:

- JavaScript on a webpage may not read/write arbitrary files on the hard disk, copy them or execute programs. It has no direct access to OS functions.

  Modern browsers allow it to work with files, but the access is limited and only provided if the user does certain actions, like "dropping" a file into a browser window or selecting it via an `<input>` tag.

  There are ways to interact with the camera/microphone and other devices, but they require a user's explicit permission. So a JavaScript-enabled page may not sneakily enable a web-camera, observe the surroundings and send the information to the [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).

- Different tabs/windows generally do not know about each other. Sometimes they do, for example when one window uses JavaScript to open the other one. But even in this case, JavaScript from one page may not access the other page if they come from different sites (from a different domain, protocol or port).

  This is called the "Same Origin Policy". To work around that, _both pages_ must agree for data exchange and must contain special JavaScript code that handles it. We'll cover that in the tutorial.

  This limitation is, again, for the user's safety. A page from `http://anysite.com` which a user has opened must not be able to access another browser tab with the URL `http://gmail.com`, for example, and steal information from there.

- JavaScript can easily communicate over the net to the server where the current page came from. But its ability to receive data from other sites/domains is crippled. Though possible, it requires explicit agreement (expressed in HTTP headers) from the remote side. Once again, that's a safety limitation.

![](limitations.svg)

Such limitations do not exist if JavaScript is used outside of the browser, for example on a server. Modern browsers also allow plugins/extensions which may ask for extended permissions.

## What makes JavaScript unique?

There are at least _three_ great things about JavaScript:

```compare
+ Full integration with HTML/CSS.
+ Simple things are done simply.
+ Supported by all major browsers and enabled by default.
```

JavaScript is the only browser technology that combines these three things.

That's what makes JavaScript unique. That's why it's the most widespread tool for creating browser interfaces.

That said, JavaScript can be used to create servers, mobile applications, etc.

## Languages "over" JavaScript

The syntax of JavaScript does not suit everyone's needs. Different people want different features.

That's to be expected, because projects and requirements are different for everyone.

So, recently a plethora of new languages appeared, which are _transpiled_ (converted) to JavaScript before they run in the browser.

Modern tools make the transpilation very fast and transparent, actually allowing developers to code in another language and auto-converting it "under the hood".

Examples of such languages:

- [CoffeeScript](https://coffeescript.org/) is "syntactic sugar" for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
- [TypeScript](https://www.typescriptlang.org/) is concentrated on adding "strict data typing" to simplify the development and support of complex systems. It is developed by Microsoft.
- [Flow](https://flow.org/) also adds data typing, but in a different way. Developed by Facebook.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps), but also can be transpiled to JavaScript. Developed by Google.
- [Brython](https://brython.info/) is a Python transpiler to JavaScript that enables the writing of applications in pure Python without JavaScript.
- [Kotlin](https://kotlinlang.org/docs/reference/js-overview.html) is a modern, concise and safe programming language that can target the browser or Node.

There are more. Of course, even if we use one of these transpiled languages, we should also know JavaScript to really understand what we're doing.

## Summary

- JavaScript was initially created as a browser-only language, but it is now used in many other environments as well.
- Today, JavaScript has a unique position as the most widely-adopted browser language, fully integrated with HTML/CSS.
- There are many languages that get "transpiled" to JavaScript and provide certain features. It is recommended to take a look at them, at least briefly, after mastering JavaScript.
