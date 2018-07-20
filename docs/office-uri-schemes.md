---
title: Office URI 方案
manager: luken
ms.date: 01/14/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 1ea99a8f-b005-4b92-b313-923294d20fbf
ms.openlocfilehash: 834c4d2c2f47c6cc3f35423a7dfe3c13caf3d209
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774146"
---
# <a name="office-uri-schemes"></a>Office URI 方案

## <a name="11-abstract"></a>1.1 摘要

本文档定义了用于 Office 生产率应用程序的统一资源标识符 (URI) 的格式。方案在 Microsoft Office 2010 Service Pack 2 及更高版本中受支持，包括 Microsoft Office 2013 for Windows 和 Microsoft SharePoint 2013 产品。它还在 Office for iPhone、Office for iPad 和 Office for Mac 2011 中受支持。
  
## <a name="12-introduction"></a>1.2 简介

这些 URI 方案允许使用各种命令调用 Office 生产效率应用程序。每个应用程序提供一个不同的命名方案，但所有方案都遵循 URI 形成的相同规则（URI 架构）。
  
## <a name="13-uri-schema"></a>1.3 URI 架构

### <a name="full-schema"></a>完整架构

< *scheme-name*  >:<  *command-name*  >"|"<  *command-argument-descriptor*  > "|"<  *command-argument*  > 
  
本文档中定义的 URI 可能有一个或多个命令参数，其中每个都必须包括 < *command-argument-descriptor*  > 和 <  *command-argument*  > 元素，并且使用竖线 ("|") 字符分隔。当 URI 中包含多个命令参数时，必须有一个竖线 ("|") 字符将每个命令参数与后面的命令参数分隔。 
  
这些方案不包括 RFC 3986 的第 3.2 节中定义的颁发机构组件。调用本文档中指定的命令将在调用命令的系统上下文中进行。例如，当从运行 Microsoft Windows 且已安装 Microsoft Office 2013 的个人计算机调用 URI "ms-excel:ofv|u|http://contoso/Q4/budget.xls" 时，预期结果是 Microsoft Excel 本地安装将启动并传递参数，以便在只读模式下打开位于  *http://contoso/Q4/budget.xls*  的文件。请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。 
  
方案语法包括以下部分：
  
1. < *scheme-name*  >：这是指应该调用的应用程序类型。例如，ms-word: 方案名称由 Microsoft Word 注册。 
    
2. ":" 分隔符
    
3. < *command-name*  >：这描述了应用程序应执行的操作。例如，打开文档以进行查看。命令名称列表在第 1.5 节中介绍。 
    
4. "|"（竖线）分隔符
    
5. < *command-argument-descriptor*  >：此元素提供了有关命令参数关于什么内容的详细信息。 
    
6. "|"（竖线）分隔符
    
7. < *command-argument*  >：参数根据命令而有所不同。一个常见的参数是文档的 URI，通常使用 http 或 https 方案。请注意，在 <  *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。 
    
### <a name="abbreviated-schema"></a>缩写的架构

Office URI 方案的缩写形式允许发出更紧凑的请求启动指定的 Office 应用程序，以打开位于指定 URI 的资源。此缩写形式表示 < *command-name*  > "ofv" 和 <  *command-argument-descriptor*  > "u"。此架构中不允许任何其他命令或命令参数。 
  
< *scheme-name*  >:<  *command-argument*  > 
  
1. < *scheme-name*  >：应该调用的应用程序类型。例如，ms-word: 表示 Microsoft Word。 
    
2. < *command-argument*  >：应用程序应打开的资源的 URI。当前仅支持基于 http 或 https 方案的 URI。 
    
## <a name="14-scheme-names-and-office-application-registrations"></a>1.4 方案名称和 Office 应用程序注册

下面是在 Microsoft Office 应用程序中实现的方案名称的列表。安装 Microsoft Office 后，在 Windows 中注册的方案名称将由相同名称的 Office 产品处理。请注意，"ms-spd"是 SharePoint Designer 的缩写。
  
> - *ms-word:* 
    
> - *ms-powerpoint:* 
    
> - *ms-excel:* 
    
> - *ms-visio:* 
    
> - *ms-access:* 
    
> - *ms-project:* 
    
> - *ms-publisher:* 
    
> - *ms-spd:* 
    
> - *ms-infopath:* 
    
## <a name="15-commands-and-required-command-arguments"></a>1.5 命令和所需的命令参数

### <a name="view-document"></a>查看文档

下面的命令将导致应用程序在只读或查看模式下打开由 URI 引用的文档。
  
> 命令名称：ofv
    
> 命令参数描述符：u
    
> 命令参数：文档的 URI，基于 http 或 https 方案
    
> 示例： *ms-excel:ofv|u|http://contoso/Q4/budget.xls* 
    
### <a name="edit-document"></a>编辑文档

下面的命令将导致应用程序在编辑模式下打开由 URI 引用的文档。
  
> 命令名称：ofe
    
> 命令参数描述符：u
    
> 命令参数：文档的 URI，基于 http 或 https 方案
    
> 示例： *ms-powerpoint:ofe|u|http://www.fourthcoffee.com/AllHandsDeck.ppt* 
    
### <a name="new-document-from-template"></a>从模板新建文档

下面的命令将导致应用程序基于存储在指定 URI 的模板创建和打开新文档。模板文件在此过程中没有修改。可能会提供一个额外的命令参数以指定当第一次保存文件时作为保存位置提供的默认路径。用户可以选择其他位置。
  
> 命令名称：nft
    
> 命令参数描述符 1：u
    
> 命令参数 1：模板的 URI，基于 http 或 https 方案
    
> 可选命令参数描述符 2：s
    
> 可选命令参数 2：指定默认保存文件夹的 URI
    
> 示例： *ms-word:nft|u|http://cohowinery/templates/elegance.pot|s|http://cohowinery/presentations* 
    
注意，如果提供了可选默认保存位置，必须指向与模板相同的主机名称。
  
此外，SharePoint Designer 和 InfoPath 应用程序（分别实现 ms-spd: 方案和 ms-infopath: 方案）不支持"从模板新建文档"功能。
  
## <a name="16-backwards-compatibility"></a>1.6 向后兼容性

当解析 URI 以提取指定命令的合适命令参数时，Office URI 处理程序将仅使用有预期的命令参数描述符的命令参数。如果存在具有非预期参数描述符的其他参数和参数描述符对，将从 URI 中删除。此机制允许方案的以后版本添加其他命令参数，而不中断与此方案旧实现的向后兼容性。
  
## <a name="17-implementation-restrictions-on-command-arguments"></a>1.7 对命令参数的实现限制

在 Office 2013 中的当前实现上，对命令参数实施以下限制。
  
### <a name="length-limitations-on-uri-command-arguments"></a>对 URI 命令参数的长度限制

对于 URI 命令参数，最大路径长度为 256 个字符，这适用于除 Excel 以外的所有应用程序，对于 Excel 为 216 个。超过这些限制的路径长度可能在个别应用程序上受支持，建议您先进行测试，然后再部署任何依赖于此的解决方案。
  
### <a name="allowed-characters-in-uri-command-arguments"></a>URI 命令参数中的允许字符

允许的 URI 必须符合 RFC 3987 中建议的标准 - 国际化资源标识符 (IRI)。在 RFC 3986 中标记为保留的子服务不应进行百分比编码。文件名不应包含下列任一字符：\ / : ? \< \> | " 或 \*。  
  
## <a name="appendix-a---uri-scheme-registration-template-for-ms-word-scheme"></a>附录 A - MS-WORD 方案的 URI 方案注册模板
<a name="bk_addresources"> </a>

### <a name="a-3-uri-scheme-syntax"></a>A-3. URI 方案语法

> Word 方案 = "ms-word:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd
    
> open-for-edit-cmd = "ofe|u|" document-uri
    
> open-for-view-cmd = "ofv|u|" document-uri
    
> new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]
    
> document-uri = 要打开的文档的 URI 位置
    
> template-uri = 新文件将基于的模板文件的 URI 位置
    
> save-location = 应在其中创建新文档的文件夹的 URI 位置
    
### <a name="a-4-uri-scheme-semantics"></a>A-4. URI 方案语义

ms-word 方案定义打开或创建 Word 处理文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 Word 处理应用程序打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示 Word 处理应用程序在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示 Word 处理应用程序基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。
  
### <a name="a-5-applicationsprotocols-that-use-the-ms-word-uri-scheme"></a>A-5. 使用 ms-word URI 方案的应用程序/协议

Microsoft Office 2013 使用 ms-word URI 方案调用 Microsoft Word 2013 或 Microsoft Word 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-word URI 作为存储在 SharePoint 文档库中的 Word 处理文档的链接。
  
### <a name="a-6-interoperability-considerations"></a>A-6. 互操作性的注意事项

请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。
  
在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。 
  
### <a name="a-7-security-considerations"></a>A-7. 安全的注意事项

 在已注册处理程序以识别和处理 ms-word URI 的系统上，单击某个 ms-word URI 的链接将导致注册的 Word 处理应用程序启动，并指示 Word 处理应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-word URI 的 Word 处理应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。 
  
### <a name="a-8-references"></a>A-8. 引用

RFC 3987 - 国际资源标识符 (IRI)  
  
## <a name="appendix-b---uri-scheme-registration-template-for-ms-powerpoint-scheme"></a>附录 B - MS-POWERPOINT 方案的 URI 方案注册模板
<a name="bk_addresources"> </a>

### <a name="b-3-uri-scheme-syntax"></a>B-3. URI 方案语法

- PowerPoint 方案 = "ms-powerpoint:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd
    
- open-for-edit-cmd = "ofe|u|" document-uri
    
- open-for-view-cmd = "ofv|u|" document-uri
    
- new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]
    
- document-uri = 要打开的文档的 URI 位置
    
- template-uri = 新文件将基于的模板文件的 URI 位置
    
- save-location\* = 应在其中创建新文档的文件夹的 URI 位置
    
- \*save-location 是可选参数
    
### <a name="b-4-uri-scheme-semantics"></a>B-4. URI 方案语义

ms-powerpoint 方案定义打开或创建演示文稿文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示演示文稿应用程序打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示演示文稿应用程序在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示演示文稿应用程序基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。
  
### <a name="b-5-applicationsprotocols-that-use-the-ms-powerpoint-uri-scheme"></a>B-5. 使用 ms-powerpoint URI 方案的应用程序/协议

Microsoft Office 2013 使用 ms-powerpoint URI 方案调用 Microsoft PowerPoint 2013 或 Microsoft PowerPoint 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-powerpoint URI 作为存储在 SharePoint 文档库中的演示文稿文档的链接。
  
### <a name="b-6-interoperability-considerations"></a>B-6. 互操作性的注意事项

请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。
  
在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。 
  
### <a name="b-7-security-considerations"></a>B-7. 安全的注意事项

在已注册处理程序以识别和处理 ms-powerpoint URI 的系统上，单击某个 ms-powerpoint URI 的链接将导致注册的演示文稿应用程序启动，并指示演示文稿应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-powerpoint URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。
  
### <a name="b-8-references"></a>B-8. 引用

RFC 3987 - 国际资源标识符 (IRI)  
  
## <a name="appendix-c---uri-scheme-registration-template-for-ms-excel-scheme"></a>附录 C - MS-EXCEL 方案的 URI 方案注册模板
<a name="bk_addresources"> </a>

### <a name="c-3-uri-scheme-syntax"></a>C-3. URI 方案语法

> Excel 方案 = "ms-excel:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd
    
> open-for-edit-cmd = "ofe|u|" document-uri
    
> open-for-view-cmd = "ofv|u|" document-uri
    
> new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]
    
> document-uri = 要打开的文档的 URI 位置
    
> template-uri = 新文件将基于的模板文件的 URI 位置
    
> save-location\* = 应在其中创建新文档的文件夹的 URI 位置
    
> \*save-location 是可选参数
    
### <a name="c-4-uri-scheme-semantics"></a>C-4. URI 方案语义

ms-excel 方案定义打开或创建电子表格文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示电子表格应用程序打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示电子表格应用程序在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示电子表格应用程序基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。
  
### <a name="c-5-applicationsprotocols-that-use-the-ms-excel-uri-scheme"></a>C-5. 使用 ms-excel URI 方案的应用程序/协议

Microsoft Office 2013 使用 ms-excel URI 方案调用 Microsoft Excel 2013 或 Microsoft Excel 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-excel URI 作为存储在 SharePoint 文档库中的电子表格文档的链接。
  
### <a name="c-6-interoperability-considerations"></a>C-6. 互操作性的注意事项

请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。
  
在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。 
  
### <a name="c-7-security-considerations"></a>C-7. 安全的注意事项

在已注册处理程序以识别和处理 ms-excel URI 的系统上，单击某个 ms-excel URI 的链接将导致注册的电子表格应用程序启动，并指示电子表格应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-excel URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。
  
### <a name="c-8-references"></a>C-8. 引用

RFC 3987 - 国际资源标识符 (IRI)  
  
## <a name="appendix-d---uri-scheme-registration-template-for-ms-visio-scheme"></a>附录 D - MS-VISIO 方案的 URI 方案注册模板
<a name="bk_addresources"> </a>

### <a name="d-3-uri-scheme-syntax"></a>D-3. URI 方案语法

> Visio 方案 = "ms-visio:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd
    
> open-for-edit-cmd = "ofe|u|" document-uri
    
> open-for-view-cmd = "ofv|u|" document-uri
    
> new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]
    
> document-uri = 要打开的文档的 URI 位置
    
> template-uri = 新文件将基于的模板文件的 URI 位置
    
> save-location\* = 应在其中创建新文档的文件夹的 URI 位置
    
> \*save-location 是可选参数
    
### <a name="d-4-uri-scheme-semantics"></a>D-4. URI 方案语义

ms-visio 方案定义打开或创建 Microsoft Visio 文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 Visio 打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示 Visio 在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示 Visio 基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。
  
### <a name="d-5-applicationsprotocols-that-use-the-ms-visio-uri-scheme"></a>D-5. 使用 ms-visio URI 方案的应用程序/协议

Microsoft Office 2013 使用 ms-visio URI 方案调用 Microsoft Visio 2013 或 Microsoft Visio 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-visio URI 作为存储在 SharePoint 文档库中的 Visio 文档的链接。
  
### <a name="d-6-interoperability-considerations"></a>D-6. 互操作性的注意事项

请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。
  
在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。 
  
### <a name="d-7-security-considerations"></a>D-7. 安全的注意事项

在已注册处理程序以识别和处理 ms-visio URI 的系统上，单击某个 ms-visio URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-visio URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。
  
### <a name="d-8-references"></a>D-8. 引用

RFC 3987 - 国际资源标识符 (IRI)
  
## <a name="appendix-e---uri-scheme-registration-template-for-ms-access-scheme"></a>附录 E - MS-ACCESS 方案的 URI 方案注册模板
<a name="bk_addresources"> </a>

### <a name="e-3-uri-scheme-syntax"></a>E-3. URI 方案语法

> Access 方案 = "ms-access:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd
    
> open-for-edit-cmd = "ofe|u|" document-uri
    
> open-for-view-cmd = "ofv|u|" document-uri
    
> new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]
    
> document-uri = 要打开的文档的 URI 位置
    
> template-uri = 新文件将基于的模板文件的 URI 位置
    
> save-location\* = 应在其中创建新文档的文件夹的 URI 位置
    
> \*save-location 是可选参数
    
### <a name="e-4-uri-scheme-semantics"></a>E-4. URI 方案语义

ms-access 方案定义打开或创建数据库的 URI 语法。方案定义充当应在引用数据库文件中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示数据库应用程序打开位于指定 URI 的数据库以进行编辑；2) open-for-view-cmd (ofv)，此命令指示数据库应用程序在只读模式下打开位于指定 URI 的数据库；以及 3) new-from-template-cmd (nft)，此命令指示数据库应用程序基于位于指定 template-uri URI 的数据库模板创建新数据库，并将新数据库保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。
  
### <a name="e-5-applicationsprotocols-that-use-the-ms-access-uri-scheme"></a>E-5. 使用 ms-access URI 方案的应用程序/协议

Microsoft Office 2013 使用 ms-access URI 方案从网页调用 Microsoft Access 2013 或 Microsoft Access 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-access URI 作为存储在 SharePoint 文档库中的 Access 数据库的链接。
  
### <a name="e-6-interoperability-considerations"></a>E-6. 互操作性的注意事项

请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。在 \<command-argument\> 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。
  
### <a name="e-7-security-considerations"></a>E-7. 安全的注意事项

在已注册处理程序以识别和处理 ms-access URI 的系统上，单击某个 ms-access URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的数据库。注册为处理 ms-access URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开数据库。
  
### <a name="e-8-references"></a>E-8. 引用

RFC 3987 - 国际资源标识符 (IRI)  
  
## <a name="appendix-f---uri-scheme-registration-template-for-ms-project-scheme"></a>附录 F - MS-PROJECT 方案的 URI 方案注册模板
<a name="bk_addresources"> </a>

### <a name="f-3-uri-scheme-syntax"></a>F-3. URI 方案语法

> Project 方案 = "ms-project:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd
    
> open-for-edit-cmd = "ofe|u|" document-uri
    
> open-for-view-cmd = "ofv|u|" document-uri
    
> new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]
    
> document-uri = 要打开的文档的 URI 位置
    
> template-uri = 新文件将基于的模板文件的 URI 位置
    
> save-location\* = 应在其中创建新文档的文件夹的 URI 位置
    
> \*save-location 是可选参数
    
### <a name="f-4-uri-scheme-semantics"></a>F-4. URI 方案语义

ms-project 方案定义打开或创建 Microsoft Project 文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 Project 打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示 Project 在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示 Project 基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。
  
### <a name="f-5-applicationsprotocols-that-use-the-ms-project-uri-scheme"></a>F-5. 使用 ms-project URI 方案的应用程序/协议

Microsoft Office 2013 使用 ms-project URI 方案从网页调用 Microsoft Project 2013。Microsoft SharePoint 2013 使用 ms-project URI 作为存储在 SharePoint 文档库中的 Project 文档的链接。
  
### <a name="f-6-interoperability-considerations"></a>F-6. 互操作性的注意事项

请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。
  
在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。 
  
### <a name="f-7-security-considerations"></a>F-7. 安全的注意事项

在已注册处理程序以识别和处理 ms-project URI 的系统上，单击某个 ms-project URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-project URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。
  
### <a name="f-8-references"></a>F-8. 引用

RFC 3987 - 国际资源标识符 (IRI)  
  
## <a name="appendix-g---uri-scheme-registration-template-for-ms-publisher-scheme"></a>附录 G - MS-PUBLISHER 方案的 URI 方案注册模板
<a name="bk_addresources"> </a>

### <a name="g-3-uri-scheme"></a>G-3. URI 方案

> 语法 发布者方案 = "ms-publisher:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd
    
> open-for-edit-cmd = "ofe|u|" document-uri
    
> open-for-view-cmd = "ofv|u|" document-uri
    
> new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]
    
> document-uri = 要打开的文档的 URI 位置
    
> template-uri = 新文件将基于的模板文件的 URI 位置
    
> save-location\* = 应在其中创建新文档的文件夹的 URI 位置
    
> \*save-location 是可选参数
    
### <a name="g-4-uri-scheme-semantics"></a>G-4. URI 方案语义

ms-publisher 方案定义打开或创建 Microsoft Publisher 文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 Publisher 打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示 Publisher 在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示 Publisher 基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。
  
### <a name="g-5-applicationsprotocols-that-use-the-ms-publisher-uri-scheme"></a>G-5. 使用 ms-publisher URI 方案的应用程序/协议

Microsoft Office 2013 使用 ms-publisher URI 方案从网页调用 Microsoft Publisher 2013 或 Microsoft Publisher 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-publisher URI 作为存储在 SharePoint 文档库中的 Publisher 文档的链接。
  
### <a name="g-6-interoperability-considerations"></a>G-6. 互操作性的注意事项

请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。在 \<command-argument\> 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。
  
### <a name="g-7-security-considerations"></a>G-7. 安全的注意事项

在已注册处理程序以识别和处理 ms-publisher URI 的系统上，单击某个 ms-publisher URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-publisher URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。
  
### <a name="g-9-references"></a>G-9. 引用

RFC 3987 - 国际资源标识符 (IRI)  
  
## <a name="appendix-h---uri-scheme-registration-template-for-ms-spd-scheme"></a>附录 H - MS-SPD 方案的 URI 方案注册模板
<a name="bk_addresources"> </a>

### <a name="h-3-uri-scheme-syntax"></a>H-3. URI 方案语法

> SharePoint Designer 方案 = "ms-spd:" open-for-edit-cmd
    
> open-for-edit-cmd = "ofe|u|" document-uri
    
> document-uri = 要打开的文档的 URI 位置
    
### <a name="h-4-uri-scheme-semantics"></a>H-4. URI 方案语义

ms-spd 方案定义打开 Microsoft SharePoint Designer 文档的 URI 语法。方案定义充当应在引用文档中执行的指令的两个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 SharePoint Designer 打开位于指定 URI 的文档以进行编辑；以及 2) open-for-view-cmd (ofv)，此命令指示 SharePoint Designer 在只读模式下打开位于指定 URI 的文档。
  
### <a name="h-5-applicationsprotocols-that-use-the-ms-spd-uri-scheme"></a>H-5. 使用 ms-spd URI 方案的应用程序/协议

Microsoft Office 2013 使用 ms-spd URI 方案从网页调用 Microsoft SharePoint Designer 2013。Microsoft SharePoint 2013 使用 ms-spd URI 作为存储在 SharePoint 文档库中的 SharePoint Designer 文档的链接。
  
### <a name="h-6-interoperability-considerations"></a>H-6. 互操作性的注意事项

请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。
  
在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。 
  
### <a name="h-7-security-considerations"></a>H-7. 安全的注意事项

在已注册处理程序以识别和处理 ms-spd URI 的系统上，单击某个 ms-spd URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-spd URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。
  
### <a name="h-8-references"></a>H-8. 引用

RFC 3987 - 国际资源标识符 (IRI)  
  
## <a name="appendix-i---uri-scheme-registration-template-for-ms-infopath-scheme"></a>附录 I - MS-INFOPATH 方案的 URI 方案注册模板
<a name="bk_addresources"> </a>

###   <a name="i-3-uri-scheme-syntax"></a>?I-3. URI 方案语法

> Infopath 方案 = "ms-infopath:" open-for-edit-cmd | open-for-view-cmd
    
> open-for-edit-cmd = "ofe|u|" document-uri
    
> open-for-view-cmd = "ofv|u|" document-uri
    
> document-uri = 要打开的文档的 URI 位置
    
### <a name="i-4-uri-scheme-semantics"></a>I-4. URI 方案语义

ms-infopath 方案定义打开或创建 Microsoft Infopath 文档的 URI 语法。方案定义充当应在引用文档中执行的指令的两个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 Visio 打开位于指定 URI 的文档以进行编辑；以及 2) open-for-view-cmd (ofv)，此命令指示 Visio 在只读模式下打开位于指定 URI 的文档。
  
### <a name="i-5-applicationsprotocols-that-use-the-ms-infopath-uri-scheme"></a>I-5. 使用 ms-infopath URI 方案的应用程序/协议

Microsoft Office 2013 使用 ms-infopath URI 方案从网页调用 Microsoft Infopath 2013。Microsoft SharePoint 2013 使用 ms-infopath URI 作为存储在 SharePoint 文档库中的 Infopath 文档的链接。
  
### <a name="i-6-interoperability-considerations"></a>I-6. 互操作性的注意事项

请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。
  
在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。 
  
### <a name="i-7-security-considerations"></a>I-7. 安全的注意事项

在已注册处理程序以识别和处理 ms-infopath URI 的系统上，单击某个 ms-infopath URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-infopath URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。
  
### <a name="i-8-references"></a>I-8. 引用

RFC 3987 - 国际资源标识符 (IRI)  
  

