---
title: Microsoft OLE DB Persistence Provider（ADO 服务提供程序）
TOCTitle: Microsoft OLE DB Persistence Provider (ADO Service Provider)
ms:assetid: 22e41769-36eb-5a88-05ed-870938657624
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249007(v=office.15)
ms:contentKeyID: 48543719
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ee7f29fa12b7158f2886f908666fa485ddf291cd
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466962"
---
# <a name="microsoft-ole-db-persistence-provider-ado-service-provider"></a><span data-ttu-id="38c97-102">Microsoft OLE DB Persistence Provider（ADO 服务提供程序）</span><span class="sxs-lookup"><span data-stu-id="38c97-102">Microsoft OLE DB Persistence Provider (ADO Service Provider)</span></span>


<span data-ttu-id="38c97-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="38c97-103">**Applies to**: Access 2013 | Office 2013</span></span> 

<span data-ttu-id="38c97-p101">Microsoft OLE DB Persistence Provider 使您可以将 [Recordset](recordset-object-ado.md) 对象保存到文件中，而且以后可以从该文件中还原 **Recordset** 对象。架构信息、数据和待定的更改将被保留。</span><span class="sxs-lookup"><span data-stu-id="38c97-p101">The Microsoft OLE DB Persistence Provider enables you to save a [Recordset](recordset-object-ado.md) object into a file, and later restore that **Recordset** object from the file. Schema information, data, and pending changes are preserved.</span></span>

<span data-ttu-id="38c97-106">可以采用专用的 Advanced Data Table Gram (ADTG) 格式或开放式可扩展标记语言 (XML) 格式来保存 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="38c97-106">You can save the **Recordset** in either the proprietary Advanced Data Table Gram (ADTG) format, or the open Extensible Markup Language (XML) format.</span></span>

## <a name="provider-keyword"></a><span data-ttu-id="38c97-107">提供程序关键字</span><span class="sxs-lookup"><span data-stu-id="38c97-107">Provider Keyword</span></span>

<span data-ttu-id="38c97-108">若要调用此提供程序，请在连接字符串中指定以下关键字和值。</span><span class="sxs-lookup"><span data-stu-id="38c97-108">To invoke this provider, specify the following keyword and value in the connection string.</span></span>

```vb 
 
"Provider=MSPersist" 
```

## <a name="errors"></a><span data-ttu-id="38c97-109">错误</span><span class="sxs-lookup"><span data-stu-id="38c97-109">Errors</span></span>

<span data-ttu-id="38c97-110">在应用程序中，可能会检测到此提供程序发出的以下错误。</span><span class="sxs-lookup"><span data-stu-id="38c97-110">The following errors issued by this provider can be detected in your application.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="38c97-111">常量</span><span class="sxs-lookup"><span data-stu-id="38c97-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="38c97-112">说明</span><span class="sxs-lookup"><span data-stu-id="38c97-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38c97-113">E_BADSTREAM</span><span class="sxs-lookup"><span data-stu-id="38c97-113">E_BADSTREAM</span></span></p></td>
<td><p><span data-ttu-id="38c97-114">打开的文件不具备有效格式（即，格式不为 ADTG 或 XML）。</span><span class="sxs-lookup"><span data-stu-id="38c97-114">The file opened does not have a valid format (that is, the format is not ADTG or XML).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38c97-115">E_CANTPERSISTROWSET</span><span class="sxs-lookup"><span data-stu-id="38c97-115">E_CANTPERSISTROWSET</span></span></p></td>
<td><p><span data-ttu-id="38c97-116">已保存的 <strong>Recordset</strong> 对象具有防止其被存储的特征。</span><span class="sxs-lookup"><span data-stu-id="38c97-116">The <strong>Recordset</strong> object saved has characteristics that prevent it from being stored.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="38c97-117">备注</span><span class="sxs-lookup"><span data-stu-id="38c97-117">Remarks</span></span>

<span data-ttu-id="38c97-118">Microsoft OLE DB Persistence Provider 没有公开任何动态属性。</span><span class="sxs-lookup"><span data-stu-id="38c97-118">The Microsoft OLE DB Persistence Provider exposes no dynamic properties.</span></span>

<span data-ttu-id="38c97-119">当前只有参数化分级 **Recordset** 对象不能被保存。</span><span class="sxs-lookup"><span data-stu-id="38c97-119">Currently, only parameterized hierarchical **Recordset** objects cannot be saved.</span></span>

<span data-ttu-id="38c97-120">有关持久存储 **Recordset** 对象的详细信息，请参阅 [关于记录集持久化的详细信息](more-about-recordset-persistence.md)。</span><span class="sxs-lookup"><span data-stu-id="38c97-120">For more information about persistently storing **Recordset** objects, see [Recordset Persistence](more-about-recordset-persistence.md).</span></span>

<span data-ttu-id="38c97-121">使用流打开**Recordset**时, 不应指定任何其他的**Open**方法的*Source*参数以外参数。</span><span class="sxs-lookup"><span data-stu-id="38c97-121">When a stream is used to open a **Recordset**, there should be no parameters specified other than the *Source* parameter of the **Open** method.</span></span>

