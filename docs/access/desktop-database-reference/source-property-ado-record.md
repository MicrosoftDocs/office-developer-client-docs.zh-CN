---
title: Source 属性 (ADO Record)
TOCTitle: Source Property (ADO Record)
ms:assetid: f36f0f5f-4493-d8c5-db4b-c72f5031bcb3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250235(v=office.15)
ms:contentKeyID: 48548670
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c568861b684856f14c644a4ef3341eed66afd569
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466916"
---
# <a name="source-property-ado-record"></a><span data-ttu-id="58c1c-102">Source 属性 (ADO Record)</span><span class="sxs-lookup"><span data-stu-id="58c1c-102">Source Property (ADO Record)</span></span>


<span data-ttu-id="58c1c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="58c1c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="58c1c-104">指示由 [Record](record-object-ado.md) 表示的数据源或对象。</span><span class="sxs-lookup"><span data-stu-id="58c1c-104">Indicates the data source or object represented by the [Record](record-object-ado.md).</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="58c1c-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="58c1c-105">Settings and Return Values</span></span>

<span data-ttu-id="58c1c-106">设置或返回一个 **Variant** 值，指示 **Record** 表示的实体。</span><span class="sxs-lookup"><span data-stu-id="58c1c-106">Sets or returns a **Variant** value that indicates the entity represented by the **Record**.</span></span>

## <a name="remarks"></a><span data-ttu-id="58c1c-107">备注</span><span class="sxs-lookup"><span data-stu-id="58c1c-107">Remarks</span></span>

<span data-ttu-id="58c1c-108">**Source**属性返回**Record**对象的[Open](open-method-ado-record.md)方法的*Source*参数。</span><span class="sxs-lookup"><span data-stu-id="58c1c-108">The **Source** property returns the *Source* argument of the **Record** object [Open](open-method-ado-record.md) method.</span></span> <span data-ttu-id="58c1c-109">该属性可包含一个绝对或相对 URL 字符串。</span><span class="sxs-lookup"><span data-stu-id="58c1c-109">It can contain an absolute or relative URL string.</span></span> <span data-ttu-id="58c1c-110">使用绝对 URL 可直接打开 [Record](activeconnection-property-ado.md) 对象，而无需设置 **ActiveConnection** 属性。</span><span class="sxs-lookup"><span data-stu-id="58c1c-110">An absolute URL can be used without setting the [ActiveConnection](activeconnection-property-ado.md) property to directly open the **Record** object.</span></span> <span data-ttu-id="58c1c-111">此时将创建一个隐式 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="58c1c-111">An implicit **Connection** object is created in this case.</span></span>

<span data-ttu-id="58c1c-112">**Source** 属性还可包含对已打开的 **Recordset** 的引用，这将打开一个表示该 **Recordset** 中当前行的 **Record** 对象。</span><span class="sxs-lookup"><span data-stu-id="58c1c-112">The **Source** property can also contain a reference to an already open **Recordset**, which opens a **Record** object representing the current row in the **Recordset**.</span></span>

<span data-ttu-id="58c1c-113">**Source** 属性还可包含对从提供程序返回单行数据的 [Command](command-object-ado.md) 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="58c1c-113">The **Source** property could also contain a reference to a [Command](command-object-ado.md) object which returns a single row of data from the provider.</span></span>

<span data-ttu-id="58c1c-p102">如果也设置了 **ActiveConnection** 属性，则 **Source** 属性必须指向该连接范围内的某个对象。例如，在树状命名空间中，如果 **Source** 属性包含绝对 URL，则必须指向由连接字符串中的 URL 标识的节点范围之内的节点。如果 **Source** 属性包含相对 URL，则将在由 **ActiveConnection** 属性设置的上下文中对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="58c1c-p102">If the **ActiveConnection** property is also set, then the **Source** property must point to some object that exists within the scope of that connection. For example, in tree-structured namespaces, if the **Source** property contains an absolute URL, it must point to a node that exists inside the scope of the node identified by the URL in the connection string. If the **Source** property contains a relative URL, then it is validated within the context set by the **ActiveConnection** property.</span></span>

<span data-ttu-id="58c1c-117">**Record** 对象关闭时， **Source** 属性为可读/写属性， **Record** 对象打开时为只读属性。</span><span class="sxs-lookup"><span data-stu-id="58c1c-117">The **Source** property is read/write while the **Record** object is closed, and is read-only while the **Record** object is open.</span></span>


> [!NOTE]
> <P><span data-ttu-id="58c1c-p103">[!注释] 使用 http 方案的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对 URL 和相对 URL</A>。</span><span class="sxs-lookup"><span data-stu-id="58c1c-p103">URLs using the http scheme will automatically invoke the <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>. For more information, see <A href="absolute-and-relative-urls.md">Absolute and Relative URLs</A>.</span></span></P>

