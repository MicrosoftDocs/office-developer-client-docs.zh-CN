---
title: Keys 集合 (ADOX)
TOCTitle: Keys Collection (ADOX)
ms:assetid: 0d480c01-1b36-28b9-9135-51958f313995
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248854(v=office.15)
ms:contentKeyID: 48543215
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 837a81058a7d5ba871069a5d8534e870194ba92f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465927"
---
# <a name="keys-collection-adox"></a><span data-ttu-id="cef16-102">Keys 集合 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="cef16-102">Keys Collection (ADOX)</span></span>


<span data-ttu-id="cef16-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cef16-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cef16-104">包含表的所有 [Key](key-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="cef16-104">Contains all [Key](key-object-adox.md) objects of a table.</span></span>

## <a name="remarks"></a><span data-ttu-id="cef16-105">说明</span><span class="sxs-lookup"><span data-stu-id="cef16-105">Remarks</span></span>

<span data-ttu-id="cef16-p101">[Keys](append-method-adox-keys.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cef16-p101">The [Append](append-method-adox-keys.md) method for a **Keys** collection is unique for ADOX. You can:</span></span>

  - <span data-ttu-id="cef16-108">使用 **Append** 方法向集合添加新的键。</span><span class="sxs-lookup"><span data-stu-id="cef16-108">Add a new key to the collection with the **Append** method.</span></span>

<span data-ttu-id="cef16-p102">其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cef16-p102">The remaining properties and methods are standard to ADO collections. You can:</span></span>

  - <span data-ttu-id="cef16-111">使用 [Item](item-property-ado.md) 属性访问集合中的键。</span><span class="sxs-lookup"><span data-stu-id="cef16-111">Access a key in the collection with the [Item](item-property-ado.md) property.</span></span>

  - <span data-ttu-id="cef16-112">使用 [Count](count-property-ado.md) 属性返回集合中包含的键数。</span><span class="sxs-lookup"><span data-stu-id="cef16-112">Return the number of keys contained in the collection with the [Count](count-property-ado.md) property.</span></span>

  - <span data-ttu-id="cef16-113">使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除键。</span><span class="sxs-lookup"><span data-stu-id="cef16-113">Remove a key from the collection with the [Delete](delete-method-adox-collections.md) method.</span></span>

  - <span data-ttu-id="cef16-114">使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="cef16-114">Update the objects in the collection to reflect the current database's schema with the [Refresh](refresh-method-ado.md) method.</span></span>

