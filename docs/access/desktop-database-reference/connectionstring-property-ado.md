---
title: ConnectionString 属性 (ADO)
TOCTitle: ConnectionString property (ADO)
ms:assetid: c67a7daf-258f-d99d-6475-a4aa98d1e99d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249968(v=office.15)
ms:contentKeyID: 48547627
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 48e8998676a9c96bc7a6820d765a8b17a9dfafef
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882796"
---
# <a name="connectionstring-property-ado"></a><span data-ttu-id="ef4cf-102">ConnectionString 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="ef4cf-102">ConnectionString property (ADO)</span></span>


<span data-ttu-id="ef4cf-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ef4cf-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ef4cf-104">指示用于建立数据源连接的信息。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-104">Indicates the information used to establish a connection to a data source.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="ef4cf-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="ef4cf-105">Settings and return values</span></span>

<span data-ttu-id="ef4cf-106">设置或返回一个 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-106">Sets or returns a **String** value.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef4cf-107">备注</span><span class="sxs-lookup"><span data-stu-id="ef4cf-107">Remarks</span></span>

<span data-ttu-id="ef4cf-108">**ConnectionString**属性用于通过传递包含一系列用分号分隔的*参数* *= value*语句的详细的连接字符串中指定的数据源。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-108">Use the **ConnectionString** property to specify a data source by passing a detailed connection string containing a series of *argument* *= value* statements separated by semicolons.</span></span>

<span data-ttu-id="ef4cf-p101">ADO 支持 **ConnectionString** 属性的五个参数；任何其他参数都直接传递给提供程序，不需要 ADO 进行任何处理。ADO 支持的参数如下：</span><span class="sxs-lookup"><span data-stu-id="ef4cf-p101">ADO supports five arguments for the **ConnectionString** property; any other arguments pass directly to the provider without any processing by ADO. The arguments ADO supports are as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ef4cf-111">参数</span><span class="sxs-lookup"><span data-stu-id="ef4cf-111">Argument</span></span></p></th>
<th><p><span data-ttu-id="ef4cf-112">说明</span><span class="sxs-lookup"><span data-stu-id="ef4cf-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef4cf-113"><em>Provider=</em></span><span class="sxs-lookup"><span data-stu-id="ef4cf-113"><em>Provider=</em></span></span></p></td>
<td><p><span data-ttu-id="ef4cf-114">指定用于连接的提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-114">Specifies the name of a provider to use for the connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef4cf-115"><em>文件名 =</em></span><span class="sxs-lookup"><span data-stu-id="ef4cf-115"><em>File Name=</em></span></span></p></td>
<td><p><span data-ttu-id="ef4cf-116">指定包含预置连接信息的、特定于提供程序的文件（例如，持久化的数据源对象）的名称。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-116">Specifies the name of a provider-specific file (for example, a persisted data source object) containing preset connection information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef4cf-117"><em>Remote Provider =</em></span><span class="sxs-lookup"><span data-stu-id="ef4cf-117"><em>Remote Provider=</em></span></span></p></td>
<td><p><span data-ttu-id="ef4cf-p102">指定打开客户端连接时使用的提供程序的名称（仅限于远程数据服务）。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-p102">Specifies the name of a provider to use when opening a client-side connection. (Remote Data Service only.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef4cf-120"><em>远程服务器 =</em></span><span class="sxs-lookup"><span data-stu-id="ef4cf-120"><em>Remote Server=</em></span></span></p></td>
<td><p><span data-ttu-id="ef4cf-p103">指定打开客户端连接时使用的服务器的路径名称（仅限于远程数据服务）。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-p103">Specifies the path name of the server to use when opening a client-side connection. (Remote Data Service only.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef4cf-123"><em>URL=</em></span><span class="sxs-lookup"><span data-stu-id="ef4cf-123"><em>URL=</em></span></span></p></td>
<td><p><span data-ttu-id="ef4cf-124">将连接字符串指定为标识资源的绝对 URL，例如，文件或目录。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-124">Specifies the connection string as an absolute URL identifying a resource, such as a file or directory.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ef4cf-125">设置 **ConnectionString** 属性并打开 [Connection](connection-object-ado.md) 对象后，提供程序可以更改该属性的内容，例如，通过将 ADO 定义的参数名称映射到其提供程序对等项。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-125">After you set the **ConnectionString** property and open the [Connection](connection-object-ado.md) object, the provider may alter the contents of the property, for example, by mapping the ADO-defined argument names to their provider equivalents.</span></span>

<span data-ttu-id="ef4cf-126">**ConnectionString**属性自动继承使用的[Open](open-method-ado-connection.md)方法的*ConnectionString*参数，因此您可以在**Open**方法调用期间覆盖当前的**ConnectionString**属性的值。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-126">The **ConnectionString** property automatically inherits the value used for the *ConnectionString* argument of the [Open](open-method-ado-connection.md) method, so you can override the current **ConnectionString** property during the **Open** method call.</span></span>

<span data-ttu-id="ef4cf-127">由于*File Name*参数会导致 ADO 加载关联的提供程序，不能传递*Provider*和*File Name*参数。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-127">Because the *File Name* argument causes ADO to load the associated provider, you cannot pass both the *Provider* and *File Name* arguments.</span></span>

<span data-ttu-id="ef4cf-128">当连接关闭时， **ConnectionString** 属性为可读写，而当其打开时，该属性为只读。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-128">The **ConnectionString** property is read/write when the connection is closed and read-only when it is open.</span></span>

<span data-ttu-id="ef4cf-p104">**ConnectionString** 属性中重复的参数将被忽略。将使用任何参数的最后一个实例。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-p104">Duplicates of an argument in the **ConnectionString** property are ignored. The last instance of any argument is used.</span></span>

<span data-ttu-id="ef4cf-131">**远程数据服务用法**当客户端**Connection**对象上使用， **ConnectionString**属性可以包括仅*Remote Provider*和*Remote Server*参数。</span><span class="sxs-lookup"><span data-stu-id="ef4cf-131">**Remote Data Service Usage**When used on a client-side **Connection** object, the **ConnectionString** property can include only the *Remote Provider* and *Remote Server* parameters.</span></span>

