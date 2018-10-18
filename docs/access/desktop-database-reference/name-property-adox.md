---
title: Name 属性 (ADOX)
TOCTitle: Name Property (ADOX)
ms:assetid: c92a3b2b-6e3f-1ed9-c7be-bf348a0737af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249979(v=office.15)
ms:contentKeyID: 48547674
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4ea92fcca60d0c2877bf89359aac4532356a9874
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25604048"
---
# <a name="name-property-adox"></a><span data-ttu-id="677bb-102">Name 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="677bb-102">Name Property (ADOX)</span></span>


<span data-ttu-id="677bb-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="677bb-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="677bb-104">指示对象的名称。</span><span class="sxs-lookup"><span data-stu-id="677bb-104">Indicates the name of the object.</span></span>

<span data-ttu-id="677bb-105"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="677bb-105"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="677bb-106">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="677bb-106">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="677bb-107">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="677bb-107">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="677bb-108">master</span><span class="sxs-lookup"><span data-stu-id="677bb-108">master</span></span>

<span data-ttu-id="677bb-109">设置或返回一个 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="677bb-109">Sets or returns a **String** value.</span></span>

## <a name="remarks"></a><span data-ttu-id="677bb-110">备注</span><span class="sxs-lookup"><span data-stu-id="677bb-110">Remarks</span></span>

<span data-ttu-id="677bb-111">名称在一个集合中不必是唯一的。</span><span class="sxs-lookup"><span data-stu-id="677bb-111">Names do not have to be unique within a collection.</span></span>

<span data-ttu-id="677bb-p101">**Name** 属性对于 [Column](column-object-adox.md)、[Group](group-object-adox.md)、[Key](key-object-adox.md)、[Index](index-object-adox.md)、[Table](table-object-adox.md) 以及 [User](user-object-adox.md) 对象是可读写的。 **Name** 属性对于 [Catalog](catalog-object-adox.md)、[Procedure](procedure-object-adox.md) 和 [View](view-object-adox.md) 对象为只读。</span><span class="sxs-lookup"><span data-stu-id="677bb-p101">The **Name** property is read/write on [Column](column-object-adox.md), [Group](group-object-adox.md), [Key](key-object-adox.md), [Index](index-object-adox.md), [Table](table-object-adox.md), and [User](user-object-adox.md) objects. The **Name** property is read-only on [Catalog](catalog-object-adox.md), [Procedure](procedure-object-adox.md), and [View](view-object-adox.md) objects.</span></span>

<span data-ttu-id="677bb-114">对于可读写对象（**Column**、**Group**、**Key**、**Index**, **Table** 以及 **User** 对象），默认值为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="677bb-114">For read/write objects (**Column**, **Group**, **Key**, **Index**, **Table** and **User** objects), the default value is an empty string ("").</span></span>


> [!NOTE]
> <P><span data-ttu-id="677bb-115">[!注释] 对于键，此属性对于已追加到集合中的 <STRONG>Key</STRONG> 对象为只读。</span><span class="sxs-lookup"><span data-stu-id="677bb-115">For keys, this property is read-only on <STRONG>Key</STRONG> objects already appended to a collection.</span></span></P>




> [!NOTE]
> <P><span data-ttu-id="677bb-116">[!注释] 对于表，此属性对于已追加到集合中的 <STRONG>Table</STRONG> 对象为只读。</span><span class="sxs-lookup"><span data-stu-id="677bb-116">For tables, this property is read-only for <STRONG>Table</STRONG> objects already appended to a collection.</span></span></P>


