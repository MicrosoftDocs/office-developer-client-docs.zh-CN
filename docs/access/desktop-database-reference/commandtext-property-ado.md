---
title: CommandText 属性 (ADO)
TOCTitle: CommandText Property (ADO)
ms:assetid: 0debec1c-068f-0aea-fce8-e61aa39c5907
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248859(v=office.15)
ms:contentKeyID: 48543234
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231123
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 9000f069c7669872c686c013520f886d16e3619b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465573"
---
# <a name="commandtext-property-ado"></a><span data-ttu-id="931d2-102">CommandText 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="931d2-102">CommandText Property (ADO)</span></span>


<span data-ttu-id="931d2-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="931d2-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="931d2-104">指示要对提供程序发出的命令的文本。</span><span class="sxs-lookup"><span data-stu-id="931d2-104">Indicates the text of a command to be issued against a provider.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="931d2-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="931d2-105">Settings and Return Values</span></span>

<span data-ttu-id="931d2-p101">设置或返回一个包含提供程序命令的 **String** 值，如 SQL 语句、表名称、相对 URL 或存储过程调用。默认值为 ""（零长度字符串）。</span><span class="sxs-lookup"><span data-stu-id="931d2-p101">Sets or returns a **String** value that contains a provider command, such as an SQL statement, a table name, a relative URL, or a stored procedure call. Default is "" (zero-length string).</span></span>

## <a name="remarks"></a><span data-ttu-id="931d2-108">备注</span><span class="sxs-lookup"><span data-stu-id="931d2-108">Remarks</span></span>

<span data-ttu-id="931d2-p102">使用 **CommandText** 属性可以设置或返回 [Command](command-object-ado.md) 对象所表示的命令的文本。通常，这将是 SQL 语句，但也可以是提供程序能识别的任何其他类型的命令语句，如存储过程调用。SQL 语句必须是提供程序的查询处理器支持的特定语句或版本。</span><span class="sxs-lookup"><span data-stu-id="931d2-p102">Use the **CommandText** property to set or return the text of a command represented by a [Command](command-object-ado.md) object. Usually this will be an SQL statement, but can also be any other type of command statement recognized by the provider, such as a stored procedure call. An SQL statement must be of the particular dialect or version supported by the provider's query processor.</span></span>

<span data-ttu-id="931d2-112">在设置 [CommandText](prepared-property-ado.md) 属性时，如果 **Command** 对象的 **Prepared** 属性设置为 **True** ，且 **Command** 对象绑定到打开的连接，则在调用 [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 或 **Open** 方法时，ADO 会准备查询（即提供程序所存储的查询的已编译格式）。</span><span class="sxs-lookup"><span data-stu-id="931d2-112">If the [Prepared](prepared-property-ado.md) property of the **Command** object is set to **True** and the **Command** object is bound to an open connection when you set the **CommandText** property, ADO prepares the query (that is, a compiled form of the query that is stored by the provider) when you call the [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) or **Open** methods.</span></span>

<span data-ttu-id="931d2-p103">根据 [CommandType](commandtype-property-ado.md) 属性设置的不同，ADO 可能会更改 **CommandText** 属性。可以随时读取 **CommandText** 属性，以查看 ADO 将在执行期间使用的实际命令文本。</span><span class="sxs-lookup"><span data-stu-id="931d2-p103">Depending on the [CommandType](commandtype-property-ado.md) property setting, ADO may alter the **CommandText** property. You can read the **CommandText** property at any time to see the actual command text that ADO will use during execution.</span></span>

<span data-ttu-id="931d2-p104">使用 **CommandText** 属性可以设置或返回指定资源（如文件或目录）的相对 URL。该资源的相对位置由绝对 URL 显式指定，或由打开的 [Connection](connection-object-ado.md) 对象隐式指定。</span><span class="sxs-lookup"><span data-stu-id="931d2-p104">Use the **CommandText** property to set or return a relative URL that specifies a resource, such as a file or directory. The resource is relative to a location specified explicitly by an absolute URL, or implicitly by an open [Connection](connection-object-ado.md) object.</span></span>


> [!NOTE]
> <P><span data-ttu-id="931d2-p105">[!注释] 使用 http 方案的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对和相对 URL</A>。</span><span class="sxs-lookup"><span data-stu-id="931d2-p105">URLs using the http scheme will automatically invoke the <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>. For more information, see <A href="absolute-and-relative-urls.md">Absolute and Relative URLs</A>.</span></span></P>

