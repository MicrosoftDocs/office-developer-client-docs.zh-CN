---
title: Microsoft OLE DB Provider for Oracle
TOCTitle: Microsoft OLE DB Provider for Oracle
ms:assetid: 97508e3f-077f-9b85-f4dd-8dd01a201aba
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249674(v=office.15)
ms:contentKeyID: 48546465
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7e473176ae6a34d04fc316a8d5075e414f6c8e98
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868145"
---
# <a name="microsoft-ole-db-provider-for-oracle"></a><span data-ttu-id="b0d4c-102">Microsoft OLE DB Provider for Oracle</span><span class="sxs-lookup"><span data-stu-id="b0d4c-102">Microsoft OLE DB Provider for Oracle</span></span>

<span data-ttu-id="b0d4c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b0d4c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b0d4c-104">Microsoft OLE DB Provider for Oracle 允许 ADO 访问 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-104">The Microsoft OLE DB Provider for Oracle allows ADO to access Oracle databases.</span></span>

## <a name="connection-string-parameters"></a><span data-ttu-id="b0d4c-105">连接字符串参数</span><span class="sxs-lookup"><span data-stu-id="b0d4c-105">Connection String Parameters</span></span>

<span data-ttu-id="b0d4c-106">若要连接到此提供程序，请将 *ConnectionString* 属性的 [Provider](connectionstring-property-ado.md) 参数设置为：</span><span class="sxs-lookup"><span data-stu-id="b0d4c-106">To connect to this provider, set the *Provider* argument of the [ConnectionString](connectionstring-property-ado.md) property to:</span></span>

```vb 
 
MSDAORA 
```

<span data-ttu-id="b0d4c-107">读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-107">Reading the [Provider](provider-property-ado.md) property will return this string as well.</span></span>

<span data-ttu-id="b0d4c-p101">如果在 Oracle 数据库中执行包含键集或动态游标的连接查询，则将发生错误。Oracle 仅支持静态的只读游标。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-p101">If a join query with a keyset or dynamic cursor is executed in an Oracle database, an error occurs. Oracle only supports a static read-only cursor.</span></span>

## <a name="typical-connection-string"></a><span data-ttu-id="b0d4c-110">典型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="b0d4c-110">Typical Connection String</span></span>

<span data-ttu-id="b0d4c-111">此提供程序典型的连接字符串为：</span><span class="sxs-lookup"><span data-stu-id="b0d4c-111">A typical connection string for this provider is:</span></span>

```vb 
 
"Provider=MSDAORA;Data Source=serverName;User ID=userName; Password=userPassword;" 
```

<span data-ttu-id="b0d4c-112">该字符串由以下关键字组成：</span><span class="sxs-lookup"><span data-stu-id="b0d4c-112">The string consists of these keywords:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b0d4c-113">关键字</span><span class="sxs-lookup"><span data-stu-id="b0d4c-113">Keyword</span></span></p></th>
<th><p><span data-ttu-id="b0d4c-114">说明</span><span class="sxs-lookup"><span data-stu-id="b0d4c-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0d4c-115"><strong>Provider</strong></span><span class="sxs-lookup"><span data-stu-id="b0d4c-115"><strong>Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="b0d4c-116">指定 OLE DB Provider for Oracle。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-116">Specifies the OLE DB Provider for Oracle.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0d4c-117"><strong>Data Source</strong></span><span class="sxs-lookup"><span data-stu-id="b0d4c-117"><strong>Data Source</strong></span></span></p></td>
<td><p><span data-ttu-id="b0d4c-118">指定服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-118">Specifies the name of a server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0d4c-119"><strong>User ID</strong></span><span class="sxs-lookup"><span data-stu-id="b0d4c-119"><strong>User ID</strong></span></span></p></td>
<td><p><span data-ttu-id="b0d4c-120">指定用户名。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-120">Specifies the user name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0d4c-121"><strong>Password</strong></span><span class="sxs-lookup"><span data-stu-id="b0d4c-121"><strong>Password</strong></span></span></p></td>
<td><p><span data-ttu-id="b0d4c-122">指定用户密码。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-122">Specifies the user password.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-connection-parameters"></a><span data-ttu-id="b0d4c-123">提供程序特定的连接参数</span><span class="sxs-lookup"><span data-stu-id="b0d4c-123">Provider-Specific Connection Parameters</span></span>

<span data-ttu-id="b0d4c-p102">除了支持 ADO 定义的那些参数以外，该提供程序还支持几个提供程序特定的连接参数。与 ADO 连接属性一样，可以通过 [Connection](properties-collection-ado.md) 对象的 [Properties](connection-object-ado.md) 集合或将其作为 **ConnectionString** 的一部分来设置这些提供程序特定的属性。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-p102">The provider supports several provider-specific connection parameters in addition to those defined by ADO. As with the ADO connection properties, these provider-specific properties can be set via the [Properties](properties-collection-ado.md) collection of a [Connection](connection-object-ado.md) or as part of the **ConnectionString**.</span></span>

<span data-ttu-id="b0d4c-p103">这些参数在《OLE DB 程序员参考》中进行了全面介绍（[ADO 动态属性索引](ado-dynamic-property-index.md)提供了这些参数名与对应的 OLE DB 属性之间的交叉引用）。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-p103">These parameters are fully described in the OLE DB Programmer's Reference. (The [ADO Dynamic Property Index](ado-dynamic-property-index.md) provides a cross-reference between these parameter names and the corresponding OLE DB properties.)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b0d4c-128">参数</span><span class="sxs-lookup"><span data-stu-id="b0d4c-128">Parameter</span></span></p></th>
<th><p><span data-ttu-id="b0d4c-129">说明</span><span class="sxs-lookup"><span data-stu-id="b0d4c-129">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0d4c-130"><strong>Window Handle</strong></span><span class="sxs-lookup"><span data-stu-id="b0d4c-130"><strong>Window Handle</strong></span></span></p></td>
<td><p><span data-ttu-id="b0d4c-131">指示用于提示附加信息的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-131">Indicates the window handle to use to prompt for additional information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0d4c-132"><strong>Locale Identifier</strong></span><span class="sxs-lookup"><span data-stu-id="b0d4c-132"><strong>Locale Identifier</strong></span></span></p></td>
<td><p><span data-ttu-id="b0d4c-p104">指示唯一的 32 位数字（例如 1033），指定与用户的语言有关的首选项。这些首选项指示设置日期和时间格式的方式、按字母顺序对项排序的方式、比较字符串的方式等。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-p104">Indicates a unique 32-bit number (for example, 1033) that specifies preferences related to the user's language. These preferences indicate how dates and times are formatted, items are sorted alphabetically, strings are compared, and so on.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0d4c-135"><strong>OLE DB Services</strong></span><span class="sxs-lookup"><span data-stu-id="b0d4c-135"><strong>OLE DB Services</strong></span></span></p></td>
<td><p><span data-ttu-id="b0d4c-136">指示用于指定启用或禁用的各项 OLE DB 服务的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-136">Indicates a bitmask that specifies OLE DB services to enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0d4c-137"><strong>Prompt</strong></span><span class="sxs-lookup"><span data-stu-id="b0d4c-137"><strong>Prompt</strong></span></span></p></td>
<td><p><span data-ttu-id="b0d4c-138">指示在建立连接时是否提示用户。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-138">Indicates whether to prompt the user while a connection is being established.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0d4c-139"><strong>Extended Properties</strong></span><span class="sxs-lookup"><span data-stu-id="b0d4c-139"><strong>Extended Properties</strong></span></span></p></td>
<td><p><span data-ttu-id="b0d4c-p105">包含提供程序特定的扩展连接信息的字符串。仅对提供程序特定的连接信息（不能通过属性机制描述）使用此属性。</span><span class="sxs-lookup"><span data-stu-id="b0d4c-p105">A string containing provider-specific, extended connection information. Use this property only for provider-specific connection information that cannot be described through the property mechanism.</span></span></p></td>
</tr>
</tbody>
</table>

