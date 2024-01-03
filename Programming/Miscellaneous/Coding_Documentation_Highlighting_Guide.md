Tags: #ChatGPT #markdown #document #highlighting

---

# Markdown Document Highlighting Guide for Coding Documentation from ChatGPT

- __Author__: ChatGPT, Kuan-Hsien Wu
- __Contact__: jordan@c-link.com.tw
- __Date__: 2023/06/20
- __Version__: 0.1.1

# Context
Following categories reflect the nature of the highlighted items and how they relate to different aspects of your coding document.

## 1. Structuring Elements
The structural elements pertain to the organization and presentation of code and explanations.

| Item           | HTML Color (Light Mode)                                                                  | HTML Color (Dark Mode)                                                                             |
| :------------: | :--------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------: |
| Code Snippets  | <span style="background-color:LightGray;color:DarkGrey">FG:DarkGray; BG:LightGray</span> | <span style="background-color:DarkSlateGrey;color:LightGray">FG:Lightgray; BG:DarkSlateGray</span> |
| Comments       | <span style="color:Gray">Gray</span>                                                     | <span style="color:DarkGray">DarkGray</span>                                                       |

## 2. Text Formatting
Text formatting highlights important notes that need special attention.

| Item           | Style                        | HTML Color (Light Mode)                      | HTML Color (Dark Mode)                                    |
| :------------: | :--------------------------: | :------------------------------------------: | :-------------------------------------------------------: |
| Important Note | <b>Bold</b> or <i>Italic</i> | <span style="color:DarkBlue">DarkBlue</span> | <span style="color:CornFlowerblue;">CornFlowerBlue</span> |

## 3. Code Elements
Code elements encompass various elements within the code itself, including control flow, arguments, restrictions, and exceptions.

| Item                                 | HTML Color (Light Mode)                                | HTML Color (Dark Mode)                                        |
| :----------------------------------: | :------------------------------------------------:     | :-----------------------------------------------------------: |
| Flow Control                         | <span style="color:Green">Green</span>                 | <span style="color:Lime;background-color:dark">Lime</span>    |
| Assumption                           | <span style="color:SkyBlue">SkyBlue</span>             | <span style="color:DeepSkyBlue;">DeepSkyBlue</span>           |
| Input Argument                       | <span style="color:Orange">Orange</span>               | <span style="color:DarkOrange;">DarkOrange</span>             |
| Class/Function Argument              | <span style="color:Magenta">Magenta</span>             | <span style="color:MediumAquaMarine;">MediumAquaMarine</span> |
| Import Modules/Libraries Restriction | <span style="color:GoldenRod">GoldenRod</span>         | <span style="color:Gold;">Gold</span>                         |
| Limitation from Method               | <span style="color:Red">Red</span>                     | <span style="color:Tomato;">Tomato</span>                     |
| Exception to Flow                    | <span style="color:Pink">Pink</span>                   | <span style="color:MediumVioletRed;">MediumVioletRed</span>   |
| Variable Names                       | <span style="color:SeaGreen">SeaGreen</span>           | <span style="color:Teal;">Teal</span>                         |
| Constants                            | <span style="color:Maroon">Maroon</span>               | <span style="color:Purple;">Purple</span>                     |
| Function/Method Name                 | <span style="color:Navy">Navy</span>                   | <span style="color:LightSkyBlue;">LightSkyBlue</span>         |
| Return Values                        | <span style="color:DarkOrange">DarkOrange</span>       | <span style="color:OliveDrab;">OliveDrab</span>               |

## 4. Hyperlinks
Hyperlinks denote any URLs or links mentioned in the document.

| Item      | HTML Color (Light Mode)                      | HTML Color (Dark Mode)                                |
| :-------: | :------------------------------------------: | :---------------------------------------------------: |
| URL/Links | <span style="color:DarkCyan">DarkCyan</span> | <span style="color:MediumOrchid;">MediumOrchid</span> |

## 5. Close words from ChatGPT

> Categorizing the highlighted items in this way can help you visually and conceptually organize your document, making it easier for readers to navigate and comprehend the different elements within the text.

# Reference
- ChatGPT: https://openai.com/blog/chatgpt
- HTML Color Name: https://www.w3schools.com/tags/ref_colornames.asp
