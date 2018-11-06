---
title: Name 属性 (ADOX)
TOCTitle: Name property (ADOX)
ms:assetid: c92a3b2b-6e3f-1ed9-c7be-bf348a0737af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249979(v=office.15)
ms:contentKeyID: 48547674
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5c66c4e6b8fc43a27b2feb87e45ec436e3abfa49
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998915"
---
# <a name="name-property-adox"></a><span data-ttu-id="667d0-102">Name 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="667d0-102">Name property (ADOX)</span></span>

<span data-ttu-id="667d0-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="667d0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="667d0-104">指示对象的名称。</span><span class="sxs-lookup"><span data-stu-id="667d0-104">Indicates the name of the object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="667d0-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="667d0-105">Settings and return values</span></span>

<span data-ttu-id="667d0-106">设置或返回一个 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="667d0-106">Sets or returns a **String** value.</span></span>

## <a name="remarks"></a><span data-ttu-id="667d0-107">备注</span><span class="sxs-lookup"><span data-stu-id="667d0-107">Remarks</span></span>

<span data-ttu-id="667d0-108">名称在一个集合中不必是唯一的。</span><span class="sxs-lookup"><span data-stu-id="667d0-108">Names do not have to be unique within a collection.</span></span>

<span data-ttu-id="667d0-p101">**Name** 属性对于 [Column](column-object-adox.md)、[Group](group-object-adox.md)、[Key](key-object-adox.md)、[Index](index-object-adox.md)、[Table](table-object-adox.md) 以及 [User](user-object-adox.md) 对象是可读写的。 **Name** 属性对于 [Catalog](catalog-object-adox.md)、[Procedure](procedure-object-adox.md) 和 [View](view-object-adox.md) 对象为只读。</span><span class="sxs-lookup"><span data-stu-id="667d0-p101">The **Name** property is read/write on [Column](column-object-adox.md), [Group](group-object-adox.md), [Key](key-object-adox.md), [Index](index-object-adox.md), [Table](table-object-adox.md), and [User](user-object-adox.md) objects. The **Name** property is read-only on [Catalog](catalog-object-adox.md), [Procedure](procedure-object-adox.md), and [View](view-object-adox.md) objects.</span></span>

<span data-ttu-id="667d0-111">对于可读写对象（**Column**、**Group**、**Key**、**Index**, **Table** 以及 **User** 对象），默认值为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="667d0-111">For read/write objects (**Column**, **Group**, **Key**, **Index**, **Table** and **User** objects), the default value is an empty string ("").</span></span>

> [!NOTE]
> - <span data-ttu-id="667d0-112">[!注释] 对于键，此属性对于已追加到集合中的 **Key** 对象为只读。</span><span class="sxs-lookup"><span data-stu-id="667d0-112">For keys, this property is read-only on **Key** objects already appended to a collection.</span></span>
> - <span data-ttu-id="667d0-113">[!注释] 对于表，此属性对于已追加到集合中的 **Table** 对象为只读。</span><span class="sxs-lookup"><span data-stu-id="667d0-113">For tables, this property is read-only for **Table** objects already appended to a collection.</span></span>


