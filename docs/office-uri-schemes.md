---
title: Office URI 方案
manager: luken
ms.date: 01/14/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 1ea99a8f-b005-4b92-b313-923294d20fbf
ms.openlocfilehash: 71325af974e4778d65bea7d74561bde3c9c8bca2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299711"
---
# <a name="office-uri-schemes"></a><span data-ttu-id="3e979-102">Office URI 方案</span><span class="sxs-lookup"><span data-stu-id="3e979-102">Office URI Schemes</span></span>

## <a name="11-abstract"></a><span data-ttu-id="3e979-103">1.1 摘要</span><span class="sxs-lookup"><span data-stu-id="3e979-103">1.1 ABSTRACT</span></span>

<span data-ttu-id="3e979-p101">本文档定义了用于 Office 生产率应用程序的统一资源标识符 (URI) 的格式。方案在 Microsoft Office 2010 Service Pack 2 及更高版本中受支持，包括 Microsoft Office 2013 for Windows 和 Microsoft SharePoint 2013 产品。它还在 Office for iPhone、Office for iPad 和 Office for Mac 2011 中受支持。</span><span class="sxs-lookup"><span data-stu-id="3e979-p101">This document defines the format of Uniform Resource Identifiers (URIs) for office productivity applications. The scheme is supported in Microsoft Office 2010 Service Pack 2 and later, including the Microsoft Office 2013 for Windows and the Microsoft SharePoint 2013 products. It is also supported in Office for iPhone, Office for iPad, and Office for Mac 2011.</span></span>
  
## <a name="12-introduction"></a><span data-ttu-id="3e979-107">1.2 简介</span><span class="sxs-lookup"><span data-stu-id="3e979-107">1.2 INTRODUCTION</span></span>

<span data-ttu-id="3e979-p102">这些 URI 方案允许使用各种命令调用 Office 生产效率应用程序。每个应用程序提供一个不同的命名方案，但所有方案都遵循 URI 形成的相同规则（URI 架构）。</span><span class="sxs-lookup"><span data-stu-id="3e979-p102">These URI schemes allow for office productivity applications to be invoked with various commands. Each application is given a different named scheme but all schemes follow the same rules for how the URI is formed (URI Schema).</span></span>
  
## <a name="13-uri-schema"></a><span data-ttu-id="3e979-110">1.3 URI 架构</span><span class="sxs-lookup"><span data-stu-id="3e979-110">1.3 URI SCHEMA</span></span>

### <a name="full-schema"></a><span data-ttu-id="3e979-111">完整架构</span><span class="sxs-lookup"><span data-stu-id="3e979-111">Full schema</span></span>

<span data-ttu-id="3e979-112">< *scheme-name*  >:<  *command-name*  >"|"<  *command-argument-descriptor*  > "|"<  *command-argument*  ></span><span class="sxs-lookup"><span data-stu-id="3e979-112">< *scheme-name*  >:<  *command-name*  >"|"<  *command-argument-descriptor*  > "|"<  *command-argument*  ></span></span> 
  
<span data-ttu-id="3e979-p103">本文档中定义的 URI 可能有一个或多个命令参数，其中每个都必须包括 < *command-argument-descriptor*  > 和 <  *command-argument*  > 元素，并且使用竖线 ("|") 字符分隔。当 URI 中包含多个命令参数时，必须有一个竖线 ("|") 字符将每个命令参数与后面的命令参数分隔。</span><span class="sxs-lookup"><span data-stu-id="3e979-p103">A URI as defined in this document may have one or more command arguments, each of which must include both the < *command-argument-descriptor*  > and the <  *command-argument*  > elements and be delimited by the vertical bar ("|") character. When more than one command argument is included in a URI there must be a vertical bar ("|") character separating each command argument from the following command argument.</span></span> 
  
<span data-ttu-id="3e979-p104">这些方案不包括 RFC 3986 的第 3.2 节中定义的颁发机构组件。调用本文档中指定的命令将在调用命令的系统上下文中进行。例如，当从运行 Microsoft Windows 且已安装 Microsoft Office 2013 的个人计算机调用 URI "ms-excel:ofv|u|https://contoso/Q4/budget.xls" 时，预期结果是 Microsoft Excel 本地安装将启动并传递参数，以便在只读模式下打开位于  *https://contoso/Q4/budget.xls*  的文件。请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。</span><span class="sxs-lookup"><span data-stu-id="3e979-p104">These schemes do not include an authority component as defined in section 3.2 of RFC 3986. Invocation of the commands specified in this document takes place in the context of the system invoking the command. For example, when the URI "ms-excel:ofv|u|https://contoso/Q4/budget.xls" is invoked from a personal computer running Microsoft Windows with Microsoft Office 2013 installed the expected result is that the local installation of Microsoft Excel will be launched and passed arguments to open the file at  *https://contoso/Q4/budget.xls*  in read-only mode. Note that the vertical bar used as a delimiter in this specification is not among those characters identified in section 2.2 of RFC 3986 as reserved for potential use as delimiters. This is done intentionally to maximize the set of characters the URI command argument can support without a need to percent-encode those characters.</span></span> 
  
<span data-ttu-id="3e979-120">方案语法包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="3e979-120">The scheme syntax includes the following:</span></span>
  
1. <span data-ttu-id="3e979-p105">< *scheme-name*  >：这是指应该调用的应用程序类型。例如，ms-word: 方案名称由 Microsoft Word 注册。</span><span class="sxs-lookup"><span data-stu-id="3e979-p105">< *scheme-name*  >: This refers to the type of application that should be invoked. For instance, the ms-word: scheme name is registered by Microsoft Word.</span></span> 
    
2. <span data-ttu-id="3e979-123">":" 分隔符</span><span class="sxs-lookup"><span data-stu-id="3e979-123">":" separator</span></span>
    
3. <span data-ttu-id="3e979-p106">< *command-name*  >：这描述了应用程序应执行的操作。例如，打开文档以进行查看。命令名称列表在第 1.5 节中介绍。</span><span class="sxs-lookup"><span data-stu-id="3e979-p106">< *command-name*  >: This describes the actions that the application should perform. For instance, opening a document for viewing. The list of command names is described in section 1.5.</span></span> 
    
4. <span data-ttu-id="3e979-127">"|"（竖线）分隔符</span><span class="sxs-lookup"><span data-stu-id="3e979-127">"|" (vertical bar) separator</span></span>
    
5. <span data-ttu-id="3e979-128">< *command-argument-descriptor*  >：此元素提供了有关命令参数关于什么内容的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3e979-128">< *command-argument-descriptor*  >: This element gives more information about what the command argument is about.</span></span> 
    
6. <span data-ttu-id="3e979-129">"|"（竖线）分隔符</span><span class="sxs-lookup"><span data-stu-id="3e979-129">"|" (vertical bar) separator</span></span>
    
7. <span data-ttu-id="3e979-p107">< *command-argument*  >：参数根据命令而有所不同。一个常见的参数是文档的 URI，通常使用 http 或 https 方案。请注意，在 <  *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。</span><span class="sxs-lookup"><span data-stu-id="3e979-p107">< *command-argument*  >: The arguments vary depending on the command. One common argument is the URI to a document, typically using the http or https scheme. Note that within <  *command-argument*  > segments the RFC 3986 reserved characters ":" and "/" are part of the argument data, not delimiters, and are therefore included unescaped.</span></span> 
    
### <a name="abbreviated-schema"></a><span data-ttu-id="3e979-133">缩写的架构</span><span class="sxs-lookup"><span data-stu-id="3e979-133">Abbreviated schema</span></span>

<span data-ttu-id="3e979-p108">Office URI 方案的缩写形式允许发出更紧凑的请求启动指定的 Office 应用程序，以打开位于指定 URI 的资源。此缩写形式表示 < *command-name*  > "ofv" 和 <  *command-argument-descriptor*  > "u"。此架构中不允许任何其他命令或命令参数。</span><span class="sxs-lookup"><span data-stu-id="3e979-p108">An abbreviated form of the office URI schemes allows for a more compact request to launch a specified Office application to open the resource located at a given URI. This abbreviated form implies the < *command-name*  > "ofv" and the <  *command-argument-descriptor*  > "u". No further commands or command arguments are allowed in this schema.</span></span> 
  
<span data-ttu-id="3e979-137">< *scheme-name*  >:<  *command-argument*  ></span><span class="sxs-lookup"><span data-stu-id="3e979-137">< *scheme-name*  >:<  *command-argument*  ></span></span> 
  
1. <span data-ttu-id="3e979-p109">< *scheme-name*  >：应该调用的应用程序类型。例如，ms-word: 表示 Microsoft Word。</span><span class="sxs-lookup"><span data-stu-id="3e979-p109">< *scheme-name*  >: the type of application that should be invoked. For instance ms-word: for Microsoft Word.</span></span> 
    
2. <span data-ttu-id="3e979-p110">< *command-argument*  >：应用程序应打开的资源的 URI。当前仅支持基于 http 或 https 方案的 URI。</span><span class="sxs-lookup"><span data-stu-id="3e979-p110">< *command-argument*  >: URI for the resource the application should open. Currently only URIs based on the http or https scheme are supported.</span></span> 
    
## <a name="14-scheme-names-and-office-application-registrations"></a><span data-ttu-id="3e979-142">1.4 方案名称和 Office 应用程序注册</span><span class="sxs-lookup"><span data-stu-id="3e979-142">1.4 SCHEME NAMES AND OFFICE APPLICATION REGISTRATIONS</span></span>

<span data-ttu-id="3e979-p111">下面是在 Microsoft Office 应用程序中实现的方案名称的列表。安装 Microsoft Office 后，在 Windows 中注册的方案名称将由相同名称的 Office 产品处理。请注意，"ms-spd"是 SharePoint Designer 的缩写。</span><span class="sxs-lookup"><span data-stu-id="3e979-p111">The following is the list of scheme names implemented in Microsoft Office applications. When Microsoft Office is installed, each scheme name is registered with Windows to be handled by the Office product of the same name. Note that "ms-spd" is an abbreviation for SharePoint Designer.</span></span>
  
> - <span data-ttu-id="3e979-146">*ms-word:*</span><span class="sxs-lookup"><span data-stu-id="3e979-146">*ms-word:*</span></span> 
    
> - <span data-ttu-id="3e979-147">*ms-powerpoint:*</span><span class="sxs-lookup"><span data-stu-id="3e979-147">*ms-powerpoint:*</span></span> 
    
> - <span data-ttu-id="3e979-148">*ms-excel:*</span><span class="sxs-lookup"><span data-stu-id="3e979-148">*ms-excel:*</span></span> 
    
> - <span data-ttu-id="3e979-149">*ms-visio:*</span><span class="sxs-lookup"><span data-stu-id="3e979-149">*ms-visio:*</span></span> 
    
> - <span data-ttu-id="3e979-150">*ms-access:*</span><span class="sxs-lookup"><span data-stu-id="3e979-150">*ms-access:*</span></span> 
    
> - <span data-ttu-id="3e979-151">*ms-project:*</span><span class="sxs-lookup"><span data-stu-id="3e979-151">*ms-project:*</span></span> 
    
> - <span data-ttu-id="3e979-152">*ms-publisher:*</span><span class="sxs-lookup"><span data-stu-id="3e979-152">*ms-publisher:*</span></span> 
    
> - <span data-ttu-id="3e979-153">*ms-spd:*</span><span class="sxs-lookup"><span data-stu-id="3e979-153">*ms-spd:*</span></span> 
    
> - <span data-ttu-id="3e979-154">*ms-infopath:*</span><span class="sxs-lookup"><span data-stu-id="3e979-154">*ms-infopath:*</span></span> 
    
## <a name="15-commands-and-required-command-arguments"></a><span data-ttu-id="3e979-155">1.5 命令和所需的命令参数</span><span class="sxs-lookup"><span data-stu-id="3e979-155">1.5 COMMANDS AND REQUIRED COMMAND ARGUMENTS</span></span>

### <a name="view-document"></a><span data-ttu-id="3e979-156">查看文档</span><span class="sxs-lookup"><span data-stu-id="3e979-156">View Document</span></span>

<span data-ttu-id="3e979-157">下面的命令将导致应用程序在只读或查看模式下打开由 URI 引用的文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-157">The following command will cause the application to open the document referenced by the URI in a read-only or view mode.</span></span>
  
> <span data-ttu-id="3e979-158">命令名称：ofv</span><span class="sxs-lookup"><span data-stu-id="3e979-158">Command Name: ofv</span></span>
    
> <span data-ttu-id="3e979-159">命令参数描述符：u</span><span class="sxs-lookup"><span data-stu-id="3e979-159">Command argument descriptor: u</span></span>
    
> <span data-ttu-id="3e979-160">命令参数：文档的 URI，基于 http 或 https 方案</span><span class="sxs-lookup"><span data-stu-id="3e979-160">Command argument: a URI to the document, based on the http or https scheme</span></span>
    
> <span data-ttu-id="3e979-161">示例： *ms-excel:ofv|u|https://contoso/Q4/budget.xls*</span><span class="sxs-lookup"><span data-stu-id="3e979-161">Example:  *ms-excel:ofv|u|https://contoso/Q4/budget.xls*</span></span> 
    
### <a name="edit-document"></a><span data-ttu-id="3e979-162">编辑文档</span><span class="sxs-lookup"><span data-stu-id="3e979-162">Edit Document</span></span>

<span data-ttu-id="3e979-163">下面的命令将导致应用程序在编辑模式下打开由 URI 引用的文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-163">The following command will cause the application to open the document referenced by the URI in editing mode.</span></span>
  
> <span data-ttu-id="3e979-164">命令名称：ofe</span><span class="sxs-lookup"><span data-stu-id="3e979-164">Command Name: ofe</span></span>
    
> <span data-ttu-id="3e979-165">命令参数描述符：u</span><span class="sxs-lookup"><span data-stu-id="3e979-165">Command argument descriptor: u</span></span>
    
> <span data-ttu-id="3e979-166">命令参数：文档的 URI，基于 http 或 https 方案</span><span class="sxs-lookup"><span data-stu-id="3e979-166">Command argument: a URI to the document, based on the http or https scheme</span></span>
    
> <span data-ttu-id="3e979-167">示例： *ms-powerpoint:ofe|u|https://www.fourthcoffee.com/AllHandsDeck.ppt*</span><span class="sxs-lookup"><span data-stu-id="3e979-167">Example:  *ms-powerpoint:ofe|u|https://www.fourthcoffee.com/AllHandsDeck.ppt*</span></span> 
    
### <a name="new-document-from-template"></a><span data-ttu-id="3e979-168">从模板新建文档</span><span class="sxs-lookup"><span data-stu-id="3e979-168">New Document from Template</span></span>

<span data-ttu-id="3e979-p112">下面的命令将导致应用程序基于存储在指定 URI 的模板创建和打开新文档。模板文件在此过程中没有修改。可能会提供一个额外的命令参数以指定当第一次保存文件时作为保存位置提供的默认路径。用户可以选择其他位置。</span><span class="sxs-lookup"><span data-stu-id="3e979-p112">The following command will cause the application to create and open a new document based on the template stored at the specified URI. The template file is not modified in this process. An additional command argument may be supplied to specify the default path offered as a save location when the file is first saved. It is possible for the user to choose a different location.</span></span>
  
> <span data-ttu-id="3e979-173">命令名称：nft</span><span class="sxs-lookup"><span data-stu-id="3e979-173">Command Name: nft</span></span>
    
> <span data-ttu-id="3e979-174">命令参数描述符 1：u</span><span class="sxs-lookup"><span data-stu-id="3e979-174">Command argument descriptor 1: u</span></span>
    
> <span data-ttu-id="3e979-175">命令参数 1：模板的 URI，基于 http 或 https 方案</span><span class="sxs-lookup"><span data-stu-id="3e979-175">Command argument 1: a URI to the template, based on the http or https scheme</span></span>
    
> <span data-ttu-id="3e979-176">可选命令参数描述符 2：s</span><span class="sxs-lookup"><span data-stu-id="3e979-176">Optional Command argument descriptor 2: s</span></span>
    
> <span data-ttu-id="3e979-177">可选命令参数 2：指定默认保存文件夹的 URI</span><span class="sxs-lookup"><span data-stu-id="3e979-177">Optional Command argument 2: URI to specify the default save folder</span></span>
    
> <span data-ttu-id="3e979-178">示例： *ms-word:nft|u|https://cohowinery/templates/elegance.pot|s|https://cohowinery/presentations*</span><span class="sxs-lookup"><span data-stu-id="3e979-178">Example:  *ms-word:nft|u|https://cohowinery/templates/elegance.pot|s|https://cohowinery/presentations*</span></span> 
    
<span data-ttu-id="3e979-179">注意，如果提供了可选默认保存位置，必须指向与模板相同的主机名称。</span><span class="sxs-lookup"><span data-stu-id="3e979-179">As a note, if the optional default save location is supplied, it must be pointing to the same host name as the template.</span></span>
  
<span data-ttu-id="3e979-180">此外，SharePoint Designer 和 InfoPath 应用程序（分别实现 ms-spd: 方案和 ms-infopath: 方案）不支持"从模板新建文档"功能。</span><span class="sxs-lookup"><span data-stu-id="3e979-180">Additionally, the SharePoint Designer and InfoPath applications (which implement the ms-spd: scheme and ms-infopath: schemes, respectively) do not support the "new document from template" functionality.</span></span>
  
## <a name="16-backwards-compatibility"></a><span data-ttu-id="3e979-181">1.6 向后兼容性</span><span class="sxs-lookup"><span data-stu-id="3e979-181">1.6 BACKWARDS COMPATIBILITY</span></span>

<span data-ttu-id="3e979-p113">当解析 URI 以提取指定命令的合适命令参数时，Office URI 处理程序将仅使用有预期的命令参数描述符的命令参数。如果存在具有非预期参数描述符的其他参数和参数描述符对，将从 URI 中删除。此机制允许方案的以后版本添加其他命令参数，而不中断与此方案旧实现的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="3e979-p113">When parsing a URI to extract the appropriate command arguments for a given command, the Office URI handler will only use the command arguments that have the expected command argument descriptor. If there are additional pairs of arguments and argument descriptors that have unexpected argument descriptors, they will be removed from the URI. This mechanism allows future versions of the scheme to add additional command arguments without breaking backward compatibility with legacy implementations of this scheme.</span></span>
  
## <a name="17-implementation-restrictions-on-command-arguments"></a><span data-ttu-id="3e979-185">1.7 对命令参数的实现限制</span><span class="sxs-lookup"><span data-stu-id="3e979-185">1.7 IMPLEMENTATION RESTRICTIONS ON COMMAND ARGUMENTS</span></span>

<span data-ttu-id="3e979-186">在 Office 2013 中的当前实现上，对命令参数实施以下限制。</span><span class="sxs-lookup"><span data-stu-id="3e979-186">The below restrictions are placed on command arguments in its current implementation in Office 2013.</span></span>
  
### <a name="length-limitations-on-uri-command-arguments"></a><span data-ttu-id="3e979-187">对 URI 命令参数的长度限制</span><span class="sxs-lookup"><span data-stu-id="3e979-187">Length limitations on URI command arguments</span></span>

<span data-ttu-id="3e979-p114">对于 URI 命令参数，最大路径长度为 256 个字符，这适用于除 Excel 以外的所有应用程序，对于 Excel 为 216 个。超过这些限制的路径长度可能在个别应用程序上受支持，建议您先进行测试，然后再部署任何依赖于此的解决方案。</span><span class="sxs-lookup"><span data-stu-id="3e979-p114">For URI command arguments, the maximum path length is 256 characters for all apps except Excel, where the limit is 216. Path lengths greater than these may be supported on an app-by-app basis and testing is recommended before deploying any solutions that rely on this.</span></span>
  
### <a name="allowed-characters-in-uri-command-arguments"></a><span data-ttu-id="3e979-190">URI 命令参数中的允许字符</span><span class="sxs-lookup"><span data-stu-id="3e979-190">Allowed characters in URI command arguments</span></span>

<span data-ttu-id="3e979-p115">允许的 URI 必须符合 RFC 3987 中建议的标准 - 国际化资源标识符 (IRI)。在 RFC 3986 中标记为保留的子服务不应进行百分比编码。文件名不应包含下列任一字符：\ / : ? \< \> | " 或 \*。</span><span class="sxs-lookup"><span data-stu-id="3e979-p115">Allowed URIs must conform to the standards proposed in RFC 3987 - Internationalized Resource Identifiers (IRIs) . Characters identified as reserved in RFC 3986 should not be percent encoded. . Filenames must not contain any of the following characters: \ / : ? \< \> | " or \*.</span></span>  
  
## <a name="appendix-a---uri-scheme-registration-template-for-ms-word-scheme"></a><span data-ttu-id="3e979-196">附录 A - MS-WORD 方案的 URI 方案注册模板</span><span class="sxs-lookup"><span data-stu-id="3e979-196">APPENDIX A - URI SCHEME REGISTRATION TEMPLATE FOR MS-WORD SCHEME</span></span>
<span data-ttu-id="3e979-197"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="3e979-197"></span></span>

### <a name="a-3-uri-scheme-syntax"></a><span data-ttu-id="3e979-p116">A-3. URI 方案语法</span><span class="sxs-lookup"><span data-stu-id="3e979-p116">A-3. URI Scheme Syntax</span></span>

> <span data-ttu-id="3e979-200">Word 方案 = "ms-word:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span><span class="sxs-lookup"><span data-stu-id="3e979-200">Word Scheme = "ms-word:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span></span>
    
> <span data-ttu-id="3e979-201">open-for-edit-cmd = "ofe|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-201">open-for-edit-cmd = "ofe|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-202">open-for-view-cmd = "ofv|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-202">open-for-view-cmd = "ofv|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-203">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span><span class="sxs-lookup"><span data-stu-id="3e979-203">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span></span>
    
> <span data-ttu-id="3e979-204">document-uri = 要打开的文档的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-204">document-uri = URI location of document to open</span></span>
    
> <span data-ttu-id="3e979-205">template-uri = 新文件将基于的模板文件的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-205">template-uri = URI location of template file upon which new file will be based</span></span>
    
> <span data-ttu-id="3e979-206">save-location = 应在其中创建新文档的文件夹的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-206">save-location = URI location of folder in which new document should be created</span></span>
    
### <a name="a-4-uri-scheme-semantics"></a><span data-ttu-id="3e979-p117">A-4. URI 方案语义</span><span class="sxs-lookup"><span data-stu-id="3e979-p117">A-4. URI Scheme Semantics</span></span>

<span data-ttu-id="3e979-p118">ms-word 方案定义打开或创建 Word 处理文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 Word 处理应用程序打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示 Word 处理应用程序在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示 Word 处理应用程序基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。</span><span class="sxs-lookup"><span data-stu-id="3e979-p118">The ms-word scheme defines a URI syntax for opening or creating a word processing document. The scheme defines three commands that serve as instructions regarding what should be done with the referenced document. The commands are 1) open-for-edit-cmd (ofe), which instructs a word processing application to open the document at the specified URI for editing; 2) open-for-view-cmd (ofv), which instructs a word processing application to open the document at the specified URI in a read-only mode; and 3) new-from-template-cmd (nft), which instructs a word processing application to create a new document based on the document template located at the specified template-uri URI and save the new document either in the location specified in the optional save-location URI or, in the absence of that optional URI, in the default document library location.</span></span>
  
### <a name="a-5-applicationsprotocols-that-use-the-ms-word-uri-scheme"></a><span data-ttu-id="3e979-p119">A-5. 使用 ms-word URI 方案的应用程序/协议</span><span class="sxs-lookup"><span data-stu-id="3e979-p119">A-5. Applications/Protocols that use the ms-word URI Scheme</span></span>

<span data-ttu-id="3e979-p120">Microsoft Office 2013 使用 ms-word URI 方案调用 Microsoft Word 2013 或 Microsoft Word 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-word URI 作为存储在 SharePoint 文档库中的 Word 处理文档的链接。</span><span class="sxs-lookup"><span data-stu-id="3e979-p120">The ms-word URI Scheme is used by Microsoft Office 2013 to invoke Microsoft Word 2013 or Microsoft Word 2010 with Service Pack 2. Microsoft SharePoint 2013 uses ms-word URIs as links to word processing documents stored in SharePoint document libraries.</span></span>
  
### <a name="a-6-interoperability-considerations"></a><span data-ttu-id="3e979-p121">A-6. 互操作性的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p121">A-6. Interoperability Considerations</span></span>

<span data-ttu-id="3e979-p122">请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。</span><span class="sxs-lookup"><span data-stu-id="3e979-p122">Note that the vertical bar used as a delimiter in this specification is not among those characters identified in section 2.2 of RFC 3986 as reserved for potential use as delimiters.. This is done intentionally to maximize the set of characters the URI command argument can support without a need to percent-encode those characters.</span></span>
  
<span data-ttu-id="3e979-220">在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。</span><span class="sxs-lookup"><span data-stu-id="3e979-220">Within < *command-argument*  > segments the RFC 3986 reserved characters ":" and "/" are part of the argument data, not delimiters, and are therefore included unescaped.</span></span> 
  
### <a name="a-7-security-considerations"></a><span data-ttu-id="3e979-p123">A-7. 安全的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p123">A-7. Security Considerations</span></span>

 <span data-ttu-id="3e979-p124">在已注册处理程序以识别和处理 ms-word URI 的系统上，单击某个 ms-word URI 的链接将导致注册的 Word 处理应用程序启动，并指示 Word 处理应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-word URI 的 Word 处理应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-p124">On systems that have registered handlers to recognize and act on ms-word URIs, clicking on a link to an ms-word URI will cause the registered word processing application to be launched, with instructions to the word processing application to attempt to open a document at the specified URI. Word processing applications registering to process ms-word URIs should implement protections to guard against opening documents from untrusted remote systems that may include malicious code.</span></span> 
  
### <a name="a-8-references"></a><span data-ttu-id="3e979-p125">A-8. 引用</span><span class="sxs-lookup"><span data-stu-id="3e979-p125">A-8. References</span></span>

<span data-ttu-id="3e979-227">RFC 3987 - 国际资源标识符 (IRI)</span><span class="sxs-lookup"><span data-stu-id="3e979-227">RFC 3987 - International Resource Identifiers (IRIs)</span></span>  
  
## <a name="appendix-b---uri-scheme-registration-template-for-ms-powerpoint-scheme"></a><span data-ttu-id="3e979-228">附录 B - MS-POWERPOINT 方案的 URI 方案注册模板</span><span class="sxs-lookup"><span data-stu-id="3e979-228">APPENDIX B - URI SCHEME REGISTRATION TEMPLATE FOR MS-POWERPOINT SCHEME</span></span>
<span data-ttu-id="3e979-229"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="3e979-229"></span></span>

### <a name="b-3-uri-scheme-syntax"></a><span data-ttu-id="3e979-p126">B-3. URI 方案语法</span><span class="sxs-lookup"><span data-stu-id="3e979-p126">B-3. URI Scheme Syntax</span></span>

- <span data-ttu-id="3e979-232">PowerPoint 方案 = "ms-powerpoint:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span><span class="sxs-lookup"><span data-stu-id="3e979-232">PowerPoint Scheme = "ms-powerpoint:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span></span>
    
- <span data-ttu-id="3e979-233">open-for-edit-cmd = "ofe|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-233">open-for-edit-cmd = "ofe|u|" document-uri</span></span>
    
- <span data-ttu-id="3e979-234">open-for-view-cmd = "ofv|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-234">open-for-view-cmd = "ofv|u|" document-uri</span></span>
    
- <span data-ttu-id="3e979-235">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span><span class="sxs-lookup"><span data-stu-id="3e979-235">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span></span>
    
- <span data-ttu-id="3e979-236">document-uri = 要打开的文档的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-236">document-uri = URI location of document to open</span></span>
    
- <span data-ttu-id="3e979-237">template-uri = 新文件将基于的模板文件的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-237">template-uri = URI location of template file upon which new file will be based</span></span>
    
- <span data-ttu-id="3e979-238">save-location\* = 应在其中创建新文档的文件夹的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-238">save-location\* = URI location of folder in which new document should be created</span></span>
    
- <span data-ttu-id="3e979-239">\*save-location 是可选参数</span><span class="sxs-lookup"><span data-stu-id="3e979-239">\*save-location is an optional parameter</span></span>
    
### <a name="b-4-uri-scheme-semantics"></a><span data-ttu-id="3e979-p127">B-4. URI 方案语义</span><span class="sxs-lookup"><span data-stu-id="3e979-p127">B-4. URI Scheme Semantics</span></span>

<span data-ttu-id="3e979-p128">ms-powerpoint 方案定义打开或创建演示文稿文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示演示文稿应用程序打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示演示文稿应用程序在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示演示文稿应用程序基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。</span><span class="sxs-lookup"><span data-stu-id="3e979-p128">The ms-powerpoint scheme defines a URI syntax for opening or creating a presentation document. The scheme defines three commands that serve as instructions regarding what should be done with the referenced document. The commands are 1) open-for-edit-cmd (ofe), which instructs a presentation application to open the document at the specified URI for editing; 2) open-for-view-cmd (ofv), which instructs a presentation application to open the document at the specified URI in a read-only mode; and 3) new-from-template-cmd (nft), which instructs a presentation application to create a new document based on the document template located at the specified template-uri URI and save the new document either in the location specified in the optional save-location URI or, in the absence of that optional URI, in the default document library location.</span></span>
  
### <a name="b-5-applicationsprotocols-that-use-the-ms-powerpoint-uri-scheme"></a><span data-ttu-id="3e979-p129">B-5. 使用 ms-powerpoint URI 方案的应用程序/协议</span><span class="sxs-lookup"><span data-stu-id="3e979-p129">B-5. Applications/Protocols that use the ms-powerpoint URI Scheme</span></span>

<span data-ttu-id="3e979-p130">Microsoft Office 2013 使用 ms-powerpoint URI 方案调用 Microsoft PowerPoint 2013 或 Microsoft PowerPoint 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-powerpoint URI 作为存储在 SharePoint 文档库中的演示文稿文档的链接。</span><span class="sxs-lookup"><span data-stu-id="3e979-p130">The ms-powerpoint URI Scheme is used by Microsoft Office 2013 to invoke Microsoft PowerPoint 2013 or Microsoft PowerPoint 2010 with Service Pack 2. Microsoft SharePoint 2013 uses ms-powerpoint URIs as links to presentation documents stored in SharePoint document libraries.</span></span>
  
### <a name="b-6-interoperability-considerations"></a><span data-ttu-id="3e979-p131">B-6. 互操作性的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p131">B-6. Interoperability Considerations</span></span>

<span data-ttu-id="3e979-p132">请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。</span><span class="sxs-lookup"><span data-stu-id="3e979-p132">Note that the vertical bar used as a delimiter in this specification is not among those characters identified in section 2.2 of RFC 3986 as reserved for potential use as delimiters. This is done intentionally to maximize the set of characters the URI command argument can support without a need to percent-encode those characters.</span></span>
  
<span data-ttu-id="3e979-253">在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。</span><span class="sxs-lookup"><span data-stu-id="3e979-253">Within < *command-argument*  > segments the RFC 3986 reserved characters ":" and "/" are part of the argument data, not delimiters, and are therefore included unescaped.</span></span> 
  
### <a name="b-7-security-considerations"></a><span data-ttu-id="3e979-p133">B-7. 安全的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p133">B-7. Security Considerations</span></span>

<span data-ttu-id="3e979-p134">在已注册处理程序以识别和处理 ms-powerpoint URI 的系统上，单击某个 ms-powerpoint URI 的链接将导致注册的演示文稿应用程序启动，并指示演示文稿应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-powerpoint URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-p134">On systems that have registered handlers to recognize and act on ms-powerpoint URIs, clicking on a link to an ms-powerpoint URI will cause the registered presentation application to be launched, with instructions to the application to attempt to open a document at the specified URI. Applications registering to process ms-powerpoint URIs should implement protections to guard against opening documents from untrusted remote systems that may include malicious code.</span></span>
  
### <a name="b-8-references"></a><span data-ttu-id="3e979-p135">B-8. 引用</span><span class="sxs-lookup"><span data-stu-id="3e979-p135">B-8. References</span></span>

<span data-ttu-id="3e979-260">RFC 3987 - 国际资源标识符 (IRI)</span><span class="sxs-lookup"><span data-stu-id="3e979-260">RFC 3987 - International Resource Identifiers (IRIs)</span></span>  
  
## <a name="appendix-c---uri-scheme-registration-template-for-ms-excel-scheme"></a><span data-ttu-id="3e979-261">附录 C - MS-EXCEL 方案的 URI 方案注册模板</span><span class="sxs-lookup"><span data-stu-id="3e979-261">APPENDIX C - URI SCHEME REGISTRATION TEMPLATE FOR MS-EXCEL SCHEME</span></span>
<span data-ttu-id="3e979-262"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="3e979-262"></span></span>

### <a name="c-3-uri-scheme-syntax"></a><span data-ttu-id="3e979-p136">C-3. URI 方案语法</span><span class="sxs-lookup"><span data-stu-id="3e979-p136">C-3. URI Scheme Syntax</span></span>

> <span data-ttu-id="3e979-265">Excel 方案 = "ms-excel:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span><span class="sxs-lookup"><span data-stu-id="3e979-265">Excel Scheme = "ms-excel:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span></span>
    
> <span data-ttu-id="3e979-266">open-for-edit-cmd = "ofe|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-266">open-for-edit-cmd = "ofe|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-267">open-for-view-cmd = "ofv|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-267">open-for-view-cmd = "ofv|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-268">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span><span class="sxs-lookup"><span data-stu-id="3e979-268">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span></span>
    
> <span data-ttu-id="3e979-269">document-uri = 要打开的文档的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-269">document-uri = URI location of document to open</span></span>
    
> <span data-ttu-id="3e979-270">template-uri = 新文件将基于的模板文件的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-270">template-uri = URI location of template file upon which new file will be based</span></span>
    
> <span data-ttu-id="3e979-271">save-location\* = 应在其中创建新文档的文件夹的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-271">save-location\* = URI location of folder in which new document should be created</span></span>
    
> <span data-ttu-id="3e979-272">\*save-location 是可选参数</span><span class="sxs-lookup"><span data-stu-id="3e979-272">\*save-location is an optional parameter</span></span>
    
### <a name="c-4-uri-scheme-semantics"></a><span data-ttu-id="3e979-p137">C-4. URI 方案语义</span><span class="sxs-lookup"><span data-stu-id="3e979-p137">C-4. URI Scheme Semantics</span></span>

<span data-ttu-id="3e979-p138">ms-excel 方案定义打开或创建电子表格文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示电子表格应用程序打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示电子表格应用程序在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示电子表格应用程序基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。</span><span class="sxs-lookup"><span data-stu-id="3e979-p138">The ms-excel scheme defines a URI syntax for opening or creating a spreadsheet document. The scheme defines three commands that serve as instructions regarding what should be done with the referenced document. The commands are 1) open-for-edit-cmd (ofe), which instructs a spreadsheet application to open the document at the specified URI for editing; 2) open-for-view-cmd (ofv), which instructs a spreadsheet application to open the document at the specified URI in a read-only mode; and 3) new-from-template-cmd (nft), which instructs a spreadsheet application to create a new document based on the document template located at the specified template-uri URI and save the new document either in the location specified in the optional save-location URI or, in the absence of that optional URI, in the default document library location.</span></span>
  
### <a name="c-5-applicationsprotocols-that-use-the-ms-excel-uri-scheme"></a><span data-ttu-id="3e979-p139">C-5. 使用 ms-excel URI 方案的应用程序/协议</span><span class="sxs-lookup"><span data-stu-id="3e979-p139">C-5. Applications/Protocols that use the ms-excel URI Scheme</span></span>

<span data-ttu-id="3e979-p140">Microsoft Office 2013 使用 ms-excel URI 方案调用 Microsoft Excel 2013 或 Microsoft Excel 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-excel URI 作为存储在 SharePoint 文档库中的电子表格文档的链接。</span><span class="sxs-lookup"><span data-stu-id="3e979-p140">The ms-excel URI Scheme is used by Microsoft Office 2013 to invoke Microsoft Excel 2013 or Microsoft Excel 2010 with Service Pack 2. Microsoft SharePoint 2013 uses ms-excel URIs as links to spreadsheet documents stored in SharePoint document libraries.</span></span>
  
### <a name="c-6-interoperability-considerations"></a><span data-ttu-id="3e979-p141">C-6. 互操作性的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p141">C-6. Interoperability Considerations</span></span>

<span data-ttu-id="3e979-p142">请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。</span><span class="sxs-lookup"><span data-stu-id="3e979-p142">Note that the vertical bar used as a delimiter in this specification is not among those characters identified in section 2.2 of RFC 3986 as reserved for potential use as delimiters. This is done intentionally to maximize the set of characters the URI command argument can support without a need to percent-encode those characters.</span></span>
  
<span data-ttu-id="3e979-286">在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。</span><span class="sxs-lookup"><span data-stu-id="3e979-286">Within < *command-argument*  > segments the RFC 3986 reserved characters ":" and "/" are part of the argument data, not delimiters, and are therefore included unescaped.</span></span> 
  
### <a name="c-7-security-considerations"></a><span data-ttu-id="3e979-p143">C-7. 安全的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p143">C-7. Security Considerations</span></span>

<span data-ttu-id="3e979-p144">在已注册处理程序以识别和处理 ms-excel URI 的系统上，单击某个 ms-excel URI 的链接将导致注册的电子表格应用程序启动，并指示电子表格应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-excel URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-p144">On systems that have registered handlers to recognize and act on ms-excel URIs, clicking on a link to an ms-excel URI will cause the registered spreadsheet application to be launched, with instructions to the application to attempt to open a document at the specified URI. Applications registering to process ms-excel URIs should implement protections to guard against opening documents from untrusted remote systems that may include malicious code.</span></span>
  
### <a name="c-8-references"></a><span data-ttu-id="3e979-p145">C-8. 引用</span><span class="sxs-lookup"><span data-stu-id="3e979-p145">C-8. References</span></span>

<span data-ttu-id="3e979-293">RFC 3987 - 国际资源标识符 (IRI)</span><span class="sxs-lookup"><span data-stu-id="3e979-293">RFC 3987 - International Resource Identifiers (IRIs)</span></span>  
  
## <a name="appendix-d---uri-scheme-registration-template-for-ms-visio-scheme"></a><span data-ttu-id="3e979-294">附录 D - MS-VISIO 方案的 URI 方案注册模板</span><span class="sxs-lookup"><span data-stu-id="3e979-294">APPENDIX D - URI SCHEME REGISTRATION TEMPLATE FOR MS-VISIO SCHEME</span></span>
<span data-ttu-id="3e979-295"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="3e979-295"></span></span>

### <a name="d-3-uri-scheme-syntax"></a><span data-ttu-id="3e979-p146">D-3. URI 方案语法</span><span class="sxs-lookup"><span data-stu-id="3e979-p146">D-3. URI Scheme Syntax</span></span>

> <span data-ttu-id="3e979-298">Visio 方案 = "ms-visio:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span><span class="sxs-lookup"><span data-stu-id="3e979-298">Visio Scheme = "ms-visio:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span></span>
    
> <span data-ttu-id="3e979-299">open-for-edit-cmd = "ofe|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-299">open-for-edit-cmd = "ofe|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-300">open-for-view-cmd = "ofv|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-300">open-for-view-cmd = "ofv|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-301">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span><span class="sxs-lookup"><span data-stu-id="3e979-301">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span></span>
    
> <span data-ttu-id="3e979-302">document-uri = 要打开的文档的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-302">document-uri = URI location of document to open</span></span>
    
> <span data-ttu-id="3e979-303">template-uri = 新文件将基于的模板文件的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-303">template-uri = URI location of template file upon which new file will be based</span></span>
    
> <span data-ttu-id="3e979-304">save-location\* = 应在其中创建新文档的文件夹的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-304">save-location\* = URI location of folder in which new document should be created</span></span>
    
> <span data-ttu-id="3e979-305">\*save-location 是可选参数</span><span class="sxs-lookup"><span data-stu-id="3e979-305">\*save-location is an optional parameter</span></span>
    
### <a name="d-4-uri-scheme-semantics"></a><span data-ttu-id="3e979-p147">D-4. URI 方案语义</span><span class="sxs-lookup"><span data-stu-id="3e979-p147">D-4. URI Scheme Semantics</span></span>

<span data-ttu-id="3e979-p148">ms-visio 方案定义打开或创建 Microsoft Visio 文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 Visio 打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示 Visio 在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示 Visio 基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。</span><span class="sxs-lookup"><span data-stu-id="3e979-p148">The ms-visio scheme defines a URI syntax for opening or creating a Microsoft Visio document. The scheme defines three commands that serve as instructions regarding what should be done with the referenced document. The commands are 1) open-for-edit-cmd (ofe), which instructs Visio to open the document at the specified URI for editing; 2) open-for-view-cmd (ofv), which instructs Visio to open the document at the specified URI in a read-only mode; and 3) new-from-template-cmd (nft), which instructs Visio to create a new document based on the document template located at the specified template-uri URI and save the new document either in the location specified in the optional save-location URI or, in the absence of that optional URI, in the default document library location.</span></span>
  
### <a name="d-5-applicationsprotocols-that-use-the-ms-visio-uri-scheme"></a><span data-ttu-id="3e979-p149">D-5. 使用 ms-visio URI 方案的应用程序/协议</span><span class="sxs-lookup"><span data-stu-id="3e979-p149">D-5. Applications/Protocols that use the ms-visio URI Scheme</span></span>

<span data-ttu-id="3e979-p150">Microsoft Office 2013 使用 ms-visio URI 方案调用 Microsoft Visio 2013 或 Microsoft Visio 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-visio URI 作为存储在 SharePoint 文档库中的 Visio 文档的链接。</span><span class="sxs-lookup"><span data-stu-id="3e979-p150">The ms-visio URI Scheme is used by Microsoft Office 2013 to invoke Microsoft Visio 2013 or Microsoft Visio 2010 with Service Pack 2. Microsoft SharePoint 2013 uses ms-visio URIs as links to Visio documents stored in SharePoint document libraries.</span></span>
  
### <a name="d-6-interoperability-considerations"></a><span data-ttu-id="3e979-p151">D-6. 互操作性的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p151">D-6. Interoperability Considerations</span></span>

<span data-ttu-id="3e979-p152">请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。</span><span class="sxs-lookup"><span data-stu-id="3e979-p152">Note that the vertical bar used as a delimiter in this specification is not among those characters identified in section 2.2 of RFC 3986 as reserved for potential use as delimiters. This is done intentionally to maximize the set of characters the URI command argument can support without a need to percent-encode those characters.</span></span>
  
<span data-ttu-id="3e979-319">在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。</span><span class="sxs-lookup"><span data-stu-id="3e979-319">Within < *command-argument*  > segments the RFC 3986 reserved characters ":" and "/" are part of the argument data, not delimiters, and are therefore included unescaped.</span></span> 
  
### <a name="d-7-security-considerations"></a><span data-ttu-id="3e979-p153">D-7. 安全的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p153">D-7. Security Considerations</span></span>

<span data-ttu-id="3e979-p154">在已注册处理程序以识别和处理 ms-visio URI 的系统上，单击某个 ms-visio URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-visio URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-p154">On systems that have registered handlers to recognize and act on ms-visio URIs, clicking on a link to an ms-visio URI will cause the registered application to be launched, with instructions to the application to attempt to open a document at the specified URI. Applications registering to process ms-visio URIs should implement protections to guard against opening documents from untrusted remote systems that may include malicious code.</span></span>
  
### <a name="d-8-references"></a><span data-ttu-id="3e979-p155">D-8. 引用</span><span class="sxs-lookup"><span data-stu-id="3e979-p155">D-8. References</span></span>

<span data-ttu-id="3e979-326">RFC 3987 - 国际资源标识符 (IRI)</span><span class="sxs-lookup"><span data-stu-id="3e979-326">RFC 3987 - International Resource Identifiers (IRIs)</span></span>
  
## <a name="appendix-e---uri-scheme-registration-template-for-ms-access-scheme"></a><span data-ttu-id="3e979-327">附录 E - MS-ACCESS 方案的 URI 方案注册模板</span><span class="sxs-lookup"><span data-stu-id="3e979-327">APPENDIX E - URI SCHEME REGISTRATION TEMPLATE FOR MS-ACCESS SCHEME</span></span>
<span data-ttu-id="3e979-328"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="3e979-328"></span></span>

### <a name="e-3-uri-scheme-syntax"></a><span data-ttu-id="3e979-p156">E-3. URI 方案语法</span><span class="sxs-lookup"><span data-stu-id="3e979-p156">E-3. URI Scheme Syntax</span></span>

> <span data-ttu-id="3e979-331">Access 方案 = "ms-access:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span><span class="sxs-lookup"><span data-stu-id="3e979-331">Access Scheme = "ms-access:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span></span>
    
> <span data-ttu-id="3e979-332">open-for-edit-cmd = "ofe|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-332">open-for-edit-cmd = "ofe|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-333">open-for-view-cmd = "ofv|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-333">open-for-view-cmd = "ofv|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-334">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span><span class="sxs-lookup"><span data-stu-id="3e979-334">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span></span>
    
> <span data-ttu-id="3e979-335">document-uri = 要打开的文档的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-335">document-uri = URI location of document to open</span></span>
    
> <span data-ttu-id="3e979-336">template-uri = 新文件将基于的模板文件的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-336">template-uri = URI location of template file upon which new file will be based</span></span>
    
> <span data-ttu-id="3e979-337">save-location\* = 应在其中创建新文档的文件夹的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-337">save-location\* = URI location of folder in which new document should be created</span></span>
    
> <span data-ttu-id="3e979-338">\*save-location 是可选参数</span><span class="sxs-lookup"><span data-stu-id="3e979-338">\*save-location is an optional parameter</span></span>
    
### <a name="e-4-uri-scheme-semantics"></a><span data-ttu-id="3e979-p157">E-4. URI 方案语义</span><span class="sxs-lookup"><span data-stu-id="3e979-p157">E-4. URI Scheme Semantics</span></span>

<span data-ttu-id="3e979-p158">ms-access 方案定义打开或创建数据库的 URI 语法。方案定义充当应在引用数据库文件中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示数据库应用程序打开位于指定 URI 的数据库以进行编辑；2) open-for-view-cmd (ofv)，此命令指示数据库应用程序在只读模式下打开位于指定 URI 的数据库；以及 3) new-from-template-cmd (nft)，此命令指示数据库应用程序基于位于指定 template-uri URI 的数据库模板创建新数据库，并将新数据库保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。</span><span class="sxs-lookup"><span data-stu-id="3e979-p158">The ms-access scheme defines a URI syntax for opening or creating a database. The scheme defines three commands that serve as instructions regarding what should be done with the referenced database file. The commands are 1) open-for-edit-cmd (ofe), which instructs the database application to open the database at the specified URI for editing; 2) open-for-view-cmd (ofv), which instructs the database application to open the database at the specified URI in a read-only mode; and 3) new-from-template-cmd (nft), which instructs the database application to create a new database based on the template located at the specified template-uri URI and save the new database either in the location specified in the optional save-location URI or, in the absence of that optional URI, in the default document library location.</span></span>
  
### <a name="e-5-applicationsprotocols-that-use-the-ms-access-uri-scheme"></a><span data-ttu-id="3e979-p159">E-5. 使用 ms-access URI 方案的应用程序/协议</span><span class="sxs-lookup"><span data-stu-id="3e979-p159">E-5. Applications/Protocols that use the ms-access URI Scheme</span></span>

<span data-ttu-id="3e979-p160">Microsoft Office 2013 使用 ms-access URI 方案从网页调用 Microsoft Access 2013 或 Microsoft Access 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-access URI 作为存储在 SharePoint 文档库中的 Access 数据库的链接。</span><span class="sxs-lookup"><span data-stu-id="3e979-p160">The ms-access URI Scheme is used by Microsoft Office 2013 to invoke Microsoft Access 2013 or Microsoft Access 2010 with Service Pack 2 from web pages. Microsoft SharePoint 2013 uses ms-access URIs as links to Access databases stored in SharePoint document libraries.</span></span>
  
### <a name="e-6-interoperability-considerations"></a><span data-ttu-id="3e979-p161">E-6. 互操作性的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p161">E-6. Interoperability Considerations</span></span>

<span data-ttu-id="3e979-p162">请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。在 \<command-argument\> 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。</span><span class="sxs-lookup"><span data-stu-id="3e979-p162">Note that the vertical bar used as a delimiter in this specification is not among those characters identified in section 2.2 of RFC 3986 as reserved for potential use as delimiters. This is done intentionally to maximize the set of characters the URI command argument can support without a need to percent-encode those characters. Within \<command-argument\> segments the RFC 3986 reserved characters ":" and "/" are part of the argument data, not delimiters, and are therefore included unescaped.</span></span>
  
### <a name="e-7-security-considerations"></a><span data-ttu-id="3e979-p163">E-7. 安全的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p163">E-7. Security Considerations</span></span>

<span data-ttu-id="3e979-p164">在已注册处理程序以识别和处理 ms-access URI 的系统上，单击某个 ms-access URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的数据库。注册为处理 ms-access URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开数据库。</span><span class="sxs-lookup"><span data-stu-id="3e979-p164">On systems that have registered handlers to recognize and act on ms-access URIs, clicking on a link to an ms-access URI will cause the registered application to be launched, with instructions to the application to attempt to open a database at the specified URI. Applications registering to process ms-access URIs should implement protections to guard against opening databases from untrusted remote systems that may include malicious code.</span></span>
  
### <a name="e-8-references"></a><span data-ttu-id="3e979-p165">E-8. 引用</span><span class="sxs-lookup"><span data-stu-id="3e979-p165">E-8. References</span></span>

<span data-ttu-id="3e979-359">RFC 3987 - 国际资源标识符 (IRI)</span><span class="sxs-lookup"><span data-stu-id="3e979-359">RFC 3987 - International Resource Identifiers (IRIs)</span></span>  
  
## <a name="appendix-f---uri-scheme-registration-template-for-ms-project-scheme"></a><span data-ttu-id="3e979-360">附录 F - MS-PROJECT 方案的 URI 方案注册模板</span><span class="sxs-lookup"><span data-stu-id="3e979-360">APPENDIX F - URI SCHEME REGISTRATION TEMPLATE FOR MS-PROJECT SCHEME</span></span>
<span data-ttu-id="3e979-361"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="3e979-361"></span></span>

### <a name="f-3-uri-scheme-syntax"></a><span data-ttu-id="3e979-p166">F-3. URI 方案语法</span><span class="sxs-lookup"><span data-stu-id="3e979-p166">F-3. URI Scheme Syntax</span></span>

> <span data-ttu-id="3e979-364">Project 方案 = "ms-project:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span><span class="sxs-lookup"><span data-stu-id="3e979-364">Project Scheme = "ms-project:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span></span>
    
> <span data-ttu-id="3e979-365">open-for-edit-cmd = "ofe|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-365">open-for-edit-cmd = "ofe|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-366">open-for-view-cmd = "ofv|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-366">open-for-view-cmd = "ofv|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-367">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span><span class="sxs-lookup"><span data-stu-id="3e979-367">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span></span>
    
> <span data-ttu-id="3e979-368">document-uri = 要打开的文档的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-368">document-uri = URI location of document to open</span></span>
    
> <span data-ttu-id="3e979-369">template-uri = 新文件将基于的模板文件的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-369">template-uri = URI location of template file upon which new file will be based</span></span>
    
> <span data-ttu-id="3e979-370">save-location\* = 应在其中创建新文档的文件夹的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-370">save-location\* = URI location of folder in which new document should be created</span></span>
    
> <span data-ttu-id="3e979-371">\*save-location 是可选参数</span><span class="sxs-lookup"><span data-stu-id="3e979-371">\*save-location is an optional parameter</span></span>
    
### <a name="f-4-uri-scheme-semantics"></a><span data-ttu-id="3e979-p167">F-4. URI 方案语义</span><span class="sxs-lookup"><span data-stu-id="3e979-p167">F-4. URI Scheme Semantics</span></span>

<span data-ttu-id="3e979-p168">ms-project 方案定义打开或创建 Microsoft Project 文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 Project 打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示 Project 在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示 Project 基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。</span><span class="sxs-lookup"><span data-stu-id="3e979-p168">The ms-project scheme defines a URI syntax for opening or creating a Microsoft Project document. The scheme defines three commands that serve as instructions regarding what should be done with the referenced document. The commands are 1) open-for-edit-cmd (ofe), which instructs Project to open the document at the specified URI for editing; 2) open-for-view-cmd (ofv), which instructs Project to open the document at the specified URI in a read-only mode; and 3) new-from-template-cmd (nft), which instructs Project to create a new document based on the document template located at the specified template-uri URI and save the new document either in the location specified in the optional save-location URI or, in the absence of that optional URI, in the default document library location.</span></span>
  
### <a name="f-5-applicationsprotocols-that-use-the-ms-project-uri-scheme"></a><span data-ttu-id="3e979-p169">F-5. 使用 ms-project URI 方案的应用程序/协议</span><span class="sxs-lookup"><span data-stu-id="3e979-p169">F-5. Applications/Protocols that use the ms-project URI Scheme</span></span>

<span data-ttu-id="3e979-p170">Microsoft Office 2013 使用 ms-project URI 方案从网页调用 Microsoft Project 2013。Microsoft SharePoint 2013 使用 ms-project URI 作为存储在 SharePoint 文档库中的 Project 文档的链接。</span><span class="sxs-lookup"><span data-stu-id="3e979-p170">The ms-project URI Scheme is used by Microsoft Office 2013 to invoke Microsoft Project 2013 from web pages. Microsoft SharePoint 2013 uses ms-project URIs as links to Project documents stored in SharePoint document libraries.</span></span>
  
### <a name="f-6-interoperability-considerations"></a><span data-ttu-id="3e979-p171">F-6. 互操作性的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p171">F-6. Interoperability Considerations</span></span>

<span data-ttu-id="3e979-p172">请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。</span><span class="sxs-lookup"><span data-stu-id="3e979-p172">Note that the vertical bar used as a delimiter in this specification is not among those characters identified in section 2.2 of RFC 3986 as reserved for potential use as delimiters. This is done intentionally to maximize the set of characters the URI command argument can support without a need to percent-encode those characters.</span></span>
  
<span data-ttu-id="3e979-385">在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。</span><span class="sxs-lookup"><span data-stu-id="3e979-385">Within < *command-argument*  > segments the RFC 3986 reserved characters ":" and "/" are part of the argument data, not delimiters, and are therefore included unescaped.</span></span> 
  
### <a name="f-7-security-considerations"></a><span data-ttu-id="3e979-p173">F-7. 安全的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p173">F-7. Security Considerations</span></span>

<span data-ttu-id="3e979-p174">在已注册处理程序以识别和处理 ms-project URI 的系统上，单击某个 ms-project URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-project URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-p174">On systems that have registered handlers to recognize and act on ms-project URIs, clicking on a link to an ms-project URI will cause the registered application to be launched, with instructions to the application to attempt to open a document at the specified URI. Applications registering to process ms-project URIs should implement protections to guard against opening documents from untrusted remote systems that may include malicious code.</span></span>
  
### <a name="f-8-references"></a><span data-ttu-id="3e979-p175">F-8. 引用</span><span class="sxs-lookup"><span data-stu-id="3e979-p175">F-8. References</span></span>

<span data-ttu-id="3e979-392">RFC 3987 - 国际资源标识符 (IRI)</span><span class="sxs-lookup"><span data-stu-id="3e979-392">RFC 3987 - International Resource Identifiers (IRIs)</span></span>  
  
## <a name="appendix-g---uri-scheme-registration-template-for-ms-publisher-scheme"></a><span data-ttu-id="3e979-393">附录 G - MS-PUBLISHER 方案的 URI 方案注册模板</span><span class="sxs-lookup"><span data-stu-id="3e979-393">APPENDIX G - URI SCHEME REGISTRATION TEMPLATE FOR MS-PUBLISHER SCHEME</span></span>
<span data-ttu-id="3e979-394"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="3e979-394"></span></span>

### <a name="g-3-uri-scheme"></a><span data-ttu-id="3e979-p176">G-3. URI 方案</span><span class="sxs-lookup"><span data-stu-id="3e979-p176">G-3. URI Scheme</span></span>

> <span data-ttu-id="3e979-397">语法 发布者方案 = "ms-publisher:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span><span class="sxs-lookup"><span data-stu-id="3e979-397">Syntax Publisher Scheme = "ms-publisher:" open-for-edit-cmd | open-for-view-cmd | new-from-template-cmd</span></span>
    
> <span data-ttu-id="3e979-398">open-for-edit-cmd = "ofe|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-398">open-for-edit-cmd = "ofe|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-399">open-for-view-cmd = "ofv|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-399">open-for-view-cmd = "ofv|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-400">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span><span class="sxs-lookup"><span data-stu-id="3e979-400">new-from-template-cmd = "nft|u|" template-uri ["|s|" save-location]</span></span>
    
> <span data-ttu-id="3e979-401">document-uri = 要打开的文档的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-401">document-uri = URI location of document to open</span></span>
    
> <span data-ttu-id="3e979-402">template-uri = 新文件将基于的模板文件的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-402">template-uri = URI location of template file upon which new file will be based</span></span>
    
> <span data-ttu-id="3e979-403">save-location\* = 应在其中创建新文档的文件夹的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-403">save-location\* = URI location of folder in which new document should be created</span></span>
    
> <span data-ttu-id="3e979-404">\*save-location 是可选参数</span><span class="sxs-lookup"><span data-stu-id="3e979-404">\*save-location is an optional parameter</span></span>
    
### <a name="g-4-uri-scheme-semantics"></a><span data-ttu-id="3e979-p177">G-4. URI 方案语义</span><span class="sxs-lookup"><span data-stu-id="3e979-p177">G-4. URI Scheme Semantics</span></span>

<span data-ttu-id="3e979-p178">ms-publisher 方案定义打开或创建 Microsoft Publisher 文档的 URI 语法。方案定义充当应在引用文档中执行的指令的三个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 Publisher 打开位于指定 URI 的文档以进行编辑；2) open-for-view-cmd (ofv)，此命令指示 Publisher 在只读模式下打开位于指定 URI 的文档；以及 3) new-from-template-cmd (nft)，此命令指示 Publisher 基于位于指定 template-uri URI 的文档模板创建新文档，并将新文档保存在可选 save-location URI 指定的位置，如果没有该可选 URI，则保存在默认文档库位置。</span><span class="sxs-lookup"><span data-stu-id="3e979-p178">The ms-publisher scheme defines a URI syntax for opening or creating a Microsoft Publisher document. The scheme defines three commands that serve as instructions regarding what should be done with the referenced document. The commands are 1) open-for-edit-cmd (ofe), which instructs Publisher to open the document at the specified URI for editing; 2) open-for-view-cmd (ofv), which instructs Publisher to open the document at the specified URI in a read-only mode; and 3) new-from-template-cmd (nft), which instructs Publisher to create a new document based on the document template located at the specified template-uri URI and save the new document either in the location specified in the optional save-location URI or, in the absence of that optional URI, in the default document library location.</span></span>
  
### <a name="g-5-applicationsprotocols-that-use-the-ms-publisher-uri-scheme"></a><span data-ttu-id="3e979-p179">G-5. 使用 ms-publisher URI 方案的应用程序/协议</span><span class="sxs-lookup"><span data-stu-id="3e979-p179">G-5. Applications/Protocols that use the ms-publisher URI Scheme</span></span>

<span data-ttu-id="3e979-p180">Microsoft Office 2013 使用 ms-publisher URI 方案从网页调用 Microsoft Publisher 2013 或 Microsoft Publisher 2010 with Service Pack 2。Microsoft SharePoint 2013 使用 ms-publisher URI 作为存储在 SharePoint 文档库中的 Publisher 文档的链接。</span><span class="sxs-lookup"><span data-stu-id="3e979-p180">The ms-publisher URI Scheme is used by Microsoft Office 2013 to invoke Microsoft Publisher 2013 or Microsoft Publisher 2010 with Service Pack 2 from web pages. Microsoft SharePoint 2013 uses ms-publisher URIs as links to Publisher documents stored in SharePoint document libraries.</span></span>
  
### <a name="g-6-interoperability-considerations"></a><span data-ttu-id="3e979-p181">G-6. 互操作性的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p181">G-6. Interoperability Considerations</span></span>

<span data-ttu-id="3e979-p182">请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。在 \<command-argument\> 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。</span><span class="sxs-lookup"><span data-stu-id="3e979-p182">Note that the vertical bar used as a delimiter in this specification is not among those characters identified in section 2.2 of RFC 3986 as reserved for potential use as delimiters. This is done intentionally to maximize the set of characters the URI command argument can support without a need to percent-encode those characters. Within \<command-argument\> segments the RFC 3986 reserved characters ":" and "/" are part of the argument data, not delimiters, and are therefore included unescaped.</span></span>
  
### <a name="g-7-security-considerations"></a><span data-ttu-id="3e979-p183">G-7. 安全的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p183">G-7. Security Considerations</span></span>

<span data-ttu-id="3e979-p184">在已注册处理程序以识别和处理 ms-publisher URI 的系统上，单击某个 ms-publisher URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-publisher URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-p184">On systems that have registered handlers to recognize and act on ms-publisher URIs, clicking on a link to an ms-publisher URI will cause the registered application to be launched, with instructions to the application to attempt to open a document at the specified URI. Applications registering to process ms-publisher URIs should implement protections to guard against opening documents from untrusted remote systems that may include malicious code.</span></span>
  
### <a name="g-9-references"></a><span data-ttu-id="3e979-p185">G-9. 引用</span><span class="sxs-lookup"><span data-stu-id="3e979-p185">G-9. References</span></span>

<span data-ttu-id="3e979-425">RFC 3987 - 国际资源标识符 (IRI)</span><span class="sxs-lookup"><span data-stu-id="3e979-425">RFC 3987 - International Resource Identifiers (IRIs)</span></span>  
  
## <a name="appendix-h---uri-scheme-registration-template-for-ms-spd-scheme"></a><span data-ttu-id="3e979-426">附录 H - MS-SPD 方案的 URI 方案注册模板</span><span class="sxs-lookup"><span data-stu-id="3e979-426">APPENDIX H - URI SCHEME REGISTRATION TEMPLATE FOR MS-SPD SCHEME</span></span>
<span data-ttu-id="3e979-427"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="3e979-427"></span></span>

### <a name="h-3-uri-scheme-syntax"></a><span data-ttu-id="3e979-p186">H-3. URI 方案语法</span><span class="sxs-lookup"><span data-stu-id="3e979-p186">H-3. URI Scheme Syntax</span></span>

> <span data-ttu-id="3e979-430">SharePoint Designer 方案 = "ms-spd:" open-for-edit-cmd</span><span class="sxs-lookup"><span data-stu-id="3e979-430">SharePoint Designer Scheme = "ms-spd:" open-for-edit-cmd</span></span>
    
> <span data-ttu-id="3e979-431">open-for-edit-cmd = "ofe|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-431">open-for-edit-cmd = "ofe|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-432">document-uri = 要打开的文档的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-432">document-uri = URI location of document to open</span></span>
    
### <a name="h-4-uri-scheme-semantics"></a><span data-ttu-id="3e979-p187">H-4. URI 方案语义</span><span class="sxs-lookup"><span data-stu-id="3e979-p187">H-4. URI Scheme Semantics</span></span>

<span data-ttu-id="3e979-p188">ms-spd 方案定义打开 Microsoft SharePoint Designer 文档的 URI 语法。方案定义充当应在引用文档中执行的指令的两个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 SharePoint Designer 打开位于指定 URI 的文档以进行编辑；以及 2) open-for-view-cmd (ofv)，此命令指示 SharePoint Designer 在只读模式下打开位于指定 URI 的文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-p188">The ms-spd scheme defines a URI syntax for opening a Microsoft SharePoint Designer document. The scheme defines two commands that serve as instructions regarding what should be done with the referenced document. The commands are 1) open-for-edit-cmd (ofe), which instructs SharePoint Designer to open the document at the specified URI for editing; and 2) open-for-view-cmd (ofv), which instructs SharePoint Designer to open the document at the specified URI in a read-only mode.</span></span>
  
### <a name="h-5-applicationsprotocols-that-use-the-ms-spd-uri-scheme"></a><span data-ttu-id="3e979-p189">H-5. 使用 ms-spd URI 方案的应用程序/协议</span><span class="sxs-lookup"><span data-stu-id="3e979-p189">H-5. Applications/Protocols that use the ms-spd URI Scheme</span></span>

<span data-ttu-id="3e979-p190">Microsoft Office 2013 使用 ms-spd URI 方案从网页调用 Microsoft SharePoint Designer 2013。Microsoft SharePoint 2013 使用 ms-spd URI 作为存储在 SharePoint 文档库中的 SharePoint Designer 文档的链接。</span><span class="sxs-lookup"><span data-stu-id="3e979-p190">The ms-spd URI Scheme is used by Microsoft Office 2013 to invoke Microsoft SharePoint Designer 2013 from web pages. Microsoft SharePoint 2013 uses ms-spd URIs as links to SharePoint Designer documents stored in SharePoint document libraries.</span></span>
  
### <a name="h-6-interoperability-considerations"></a><span data-ttu-id="3e979-p191">H-6. 互操作性的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p191">H-6. Interoperability Considerations</span></span>

<span data-ttu-id="3e979-p192">请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。</span><span class="sxs-lookup"><span data-stu-id="3e979-p192">Note that the vertical bar used as a delimiter in this specification is not among those characters identified in section 2.2 of RFC 3986 as reserved for potential use as delimiters. This is done intentionally to maximize the set of characters the URI command argument can support without a need to percent-encode those characters.</span></span>
  
<span data-ttu-id="3e979-446">在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。</span><span class="sxs-lookup"><span data-stu-id="3e979-446">Within < *command-argument*  > segments the RFC 3986 reserved characters ":" and "/" are part of the argument data, not delimiters, and are therefore included unescaped.</span></span> 
  
### <a name="h-7-security-considerations"></a><span data-ttu-id="3e979-p193">H-7. 安全的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p193">H-7. Security Considerations</span></span>

<span data-ttu-id="3e979-p194">在已注册处理程序以识别和处理 ms-spd URI 的系统上，单击某个 ms-spd URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-spd URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-p194">On systems that have registered handlers to recognize and act on ms-spd URIs, clicking on a link to an ms-spd URI will cause the registered application to be launched, with instructions to the application to attempt to open a document at the specified URI. Applications registering to process ms-spd URIs should implement protections to guard against opening documents from untrusted remote systems that may include malicious code.</span></span>
  
### <a name="h-8-references"></a><span data-ttu-id="3e979-p195">H-8. 引用</span><span class="sxs-lookup"><span data-stu-id="3e979-p195">H-8. References</span></span>

<span data-ttu-id="3e979-453">RFC 3987 - 国际资源标识符 (IRI)</span><span class="sxs-lookup"><span data-stu-id="3e979-453">RFC 3987 - International Resource Identifiers (IRIs)</span></span>  
  
## <a name="appendix-i---uri-scheme-registration-template-for-ms-infopath-scheme"></a><span data-ttu-id="3e979-454">附录 I - MS-INFOPATH 方案的 URI 方案注册模板</span><span class="sxs-lookup"><span data-stu-id="3e979-454">APPENDIX I - URI SCHEME REGISTRATION TEMPLATE FOR MS-INFOPATH SCHEME</span></span>
<span data-ttu-id="3e979-455"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="3e979-455"></span></span>

###   <a name="i-3-uri-scheme-syntax"></a><span data-ttu-id="3e979-p196">?I-3. URI 方案语法</span><span class="sxs-lookup"><span data-stu-id="3e979-p196">I-3. URI Scheme Syntax</span></span>

> <span data-ttu-id="3e979-458">Infopath 方案 = "ms-infopath:" open-for-edit-cmd | open-for-view-cmd</span><span class="sxs-lookup"><span data-stu-id="3e979-458">Infopath Scheme = "ms-infopath:" open-for-edit-cmd | open-for-view-cmd</span></span>
    
> <span data-ttu-id="3e979-459">open-for-edit-cmd = "ofe|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-459">open-for-edit-cmd = "ofe|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-460">open-for-view-cmd = "ofv|u|" document-uri</span><span class="sxs-lookup"><span data-stu-id="3e979-460">open-for-view-cmd = "ofv|u|" document-uri</span></span>
    
> <span data-ttu-id="3e979-461">document-uri = 要打开的文档的 URI 位置</span><span class="sxs-lookup"><span data-stu-id="3e979-461">document-uri = URI location of document to open</span></span>
    
### <a name="i-4-uri-scheme-semantics"></a><span data-ttu-id="3e979-p197">I-4. URI 方案语义</span><span class="sxs-lookup"><span data-stu-id="3e979-p197">I-4. URI Scheme Semantics</span></span>

<span data-ttu-id="3e979-p198">ms-infopath 方案定义打开或创建 Microsoft Infopath 文档的 URI 语法。方案定义充当应在引用文档中执行的指令的两个命令，分别是：1) open-for-edit-cmd (ofe)，此命令指示 Visio 打开位于指定 URI 的文档以进行编辑；以及 2) open-for-view-cmd (ofv)，此命令指示 Visio 在只读模式下打开位于指定 URI 的文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-p198">The ms-infopath scheme defines a URI syntax for opening or creating a Microsoft Infopath document. The scheme defines two commands that serve as instructions regarding what should be done with the referenced document. The commands are 1) open-for-edit-cmd (ofe), which instructs Visio to open the document at the specified URI for editing; and 2) open-for-view-cmd (ofv), which instructs Visio to open the document at the specified URI in a read-only mode.</span></span>
  
### <a name="i-5-applicationsprotocols-that-use-the-ms-infopath-uri-scheme"></a><span data-ttu-id="3e979-p199">I-5. 使用 ms-infopath URI 方案的应用程序/协议</span><span class="sxs-lookup"><span data-stu-id="3e979-p199">I-5. Applications/Protocols that use the ms-infopath URI Scheme</span></span>

<span data-ttu-id="3e979-p200">Microsoft Office 2013 使用 ms-infopath URI 方案从网页调用 Microsoft Infopath 2013。Microsoft SharePoint 2013 使用 ms-infopath URI 作为存储在 SharePoint 文档库中的 Infopath 文档的链接。</span><span class="sxs-lookup"><span data-stu-id="3e979-p200">The ms-infopath URI Scheme is used by Microsoft Office 2013 to invoke Microsoft Infopath 2013 from web pages. Microsoft SharePoint 2013 uses ms-infopath URIs as links to Infopath documents stored in SharePoint document libraries.</span></span>
  
### <a name="i-6-interoperability-considerations"></a><span data-ttu-id="3e979-p201">I-6. 互操作性的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p201">I-6. Interoperability Considerations</span></span>

<span data-ttu-id="3e979-p202">请注意，此规范中用作分隔符的竖线没有在 RFC 3986 的第 2.2 节中标明，而是保留作为可能的分隔符。这是故意为之，以便在无需对这些字符进行百分比编码的情况下，最大限度地增加 URI 命令参数可以支持的字符集。</span><span class="sxs-lookup"><span data-stu-id="3e979-p202">Note that the vertical bar used as a delimiter in this specification is not among those characters identified in section 2.2 of RFC 3986 as reserved for potential use as delimiters. This is done intentionally to maximize the set of characters the URI command argument can support without a need to percent-encode those characters.</span></span>
  
<span data-ttu-id="3e979-475">在 < *command-argument*  > 分段中，RFC 3986 保留的字符":"和"/"是参数数据的一部分，而不是分隔符，因此包含时不应进行转义。</span><span class="sxs-lookup"><span data-stu-id="3e979-475">Within < *command-argument*  > segments the RFC 3986 reserved characters ":" and "/" are part of the argument data, not delimiters, and are therefore included unescaped.</span></span> 
  
### <a name="i-7-security-considerations"></a><span data-ttu-id="3e979-p203">I-7. 安全的注意事项</span><span class="sxs-lookup"><span data-stu-id="3e979-p203">I-7. Security Considerations</span></span>

<span data-ttu-id="3e979-p204">在已注册处理程序以识别和处理 ms-infopath URI 的系统上，单击某个 ms-infopath URI 的链接将导致注册的应用程序启动，并指示应用程序尝试打开位于指定 URI 的文档。注册为处理 ms-infopath URI 的应用程序应实施保护，以防止从可能包含恶意代码的不受信任的远程系统打开文档。</span><span class="sxs-lookup"><span data-stu-id="3e979-p204">On systems that have registered handlers to recognize and act on ms-infopath URIs, clicking on a link to an ms-infopath URI will cause the registered application to be launched, with instructions to the application to attempt to open a document at the specified URI. Applications registering to process ms-infopath URIs should implement protections to guard against opening documents from untrusted remote systems that may include malicious code.</span></span>
  
### <a name="i-8-references"></a><span data-ttu-id="3e979-p205">I-8. 引用</span><span class="sxs-lookup"><span data-stu-id="3e979-p205">I-8. References</span></span>

<span data-ttu-id="3e979-482">RFC 3987 - 国际资源标识符 (IRI)</span><span class="sxs-lookup"><span data-stu-id="3e979-482">RFC 3987 - International Resource Identifiers (IRIs)</span></span>  
  

