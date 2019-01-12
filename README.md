# Wolfram Language Server

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

>by [kenkangxgwe](mailto:kenkangxgwe@gmail.com) and [hxianglong](https://github.com/huxianglong) 

**Wolfram Language Server (WLServer)** is an implementation of the Microsoft's
[Language Server Protocol (LSP)](https://microsoft.github.io/language-server-protocol)
for Wolfram Mathematica. This server is implemented in Wolfram Mathematica
itself. From now on, you can use this extension on every [editor that supports
LSP](https://microsoft.github.io/language-server-protocol/implementors/tools/).

Our philosophy is to provide experience as good as the Wolfram frontend itself
with addition power from the editor.

We have provided the client-side code for VS Code, which is based on some slight
modifications of [Microsoft's LSP
example](https://github.com/Microsoft/vscode-extension-samples/tree/master/lsp-sample).
If you are using other tools supporting LSP, some slight modifications to the
client would certainly work too.

In the following text, I would explain some details of the project, assuming the
client is what we provided.

## Installation

**Requirements**
 <a name="ref1"></a>
- Wolfram Mathematica (11.2 or higher[<sup>1</sup>](#footnote1))  
Which is the only requirement.

To install the server, simply download this git repository.

```
git clone https://github.com/kenkangxgwe/lsp-wl.git
```

To install the client, currently, it is released on [Visual Studio Marketplace:
Wolfram Language Server](). 

## Client Settings

Once you have installed this extension, a few settings have to be done manually
in the client side (VS Code in this context) to make things work.

After the extension is launched, in the poped up window, go to **Preference ->
Settings -> User Settings -> Wolfram Language Server**.

- *Port:* The client communicates with the server through port. Feel free to use
  any port that is not occupied by other processes.

- *Theme:* Pictures are used in the poped up window for hovering, which is
transparent. So this setting is to ensure the pictures are actually visible.
This is the only way to display mathematical equations . If you use dark themes,
then choose dark[<sup>2</sup>](#footnote2). <a name="ref2"> </a>

- *WLServer Path:* Where the extension is installed.

- *Wolfram Path:* Set up the location of the Wolfram executable, which is
  *wolfram.exe* for Windows users. For example: C:\Program Files\Wolfram
  Research\Mathematica\11.3\wolfram.exe.




## Features

- *Hover:* Provide definitions for Wolfram functions and system variables, such
  as `String` and `$Path`.

- *Completion:* The completion is triggered by the client automatically.
  Currently, Wolfram functions and system variables would be displayed.

- *Completion Resolve:* Further information would be provided for the items in
  the list.

- *Diagnostics:* Syntax error would be underlined. However, the specific syntax
  error is not supported at the moment.
  
This is an early releasing, so more features are on its way. Syntax highlight is
not supported for there are already good enough highlighters like [Wolfram Language](https://marketplace.visualstudio.com/items?itemName=flipphillips.wolfram-language).

Here is a full list of [LSP features](https://microsoft.github.io/language-server-protocol/specification).

## Donations :dollar:

If you really like this extension, please donate to us! **$5(or equivalently ￥35)**, which is only the price of a
cup of coffee :coffee: would certainly brighten our day! Your donation would be
the motivation for us to move forward, thanks in advance :smile:. 

- Paypal: qwe95123@126.com
- 支付宝(附二维码): 13916018006

![支付宝二维码](https://github.com/kenkangxgwe/lsp-wl/images/alipay.jpg)

## Footnotes

<a name="footnote1"> </a> **[1]** `SocketListen[]` is used for server-client
communication, which is introduced since 11.2. [^](#ref1)


<a name="footnote2"> </a> **[2]** This reminds me of a joke making fun of
Project Managers. A programmer, who cannot put up with endless unreasonable
requests from his project manager, complained about one stupid task from him
online, which is to automatically change the theme of the app with the color of
the cell phone protectors. "How could I know the color of protectors, my
goddness, my manager is so stupid". Someone left his opnion, 'Add an option for
users to choose when launching the app, what is the color of your cell phone
protector. Then change the them accordingly.' [^](#ref2)
