---
title: IndexNulls 属性 (ADOX)
TOCTitle: IndexNulls property (ADOX)
ms:assetid: 5c78c818-c23d-5b2c-d246-531aedc639df
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249326(v=office.15)
ms:contentKeyID: 48545089
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1419abb5dc66a59594284cf319487ef980bf62f9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712881"
---
# <a name="indexnulls-property-adox"></a><span data-ttu-id="f6992-102">IndexNulls 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="f6992-102">IndexNulls property (ADOX)</span></span>


<span data-ttu-id="f6992-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f6992-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f6992-104">指示索引字段具有 null 值的记录是否有索引项。</span><span class="sxs-lookup"><span data-stu-id="f6992-104">Indicates whether records that have null values in their index fields have index entries.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="f6992-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="f6992-105">Settings and return values</span></span>

<span data-ttu-id="f6992-p101">设置和返回一个 [AllowNullsEnum](allownullsenum.md) 值。默认值为 **adIndexNullsDisallow** 。</span><span class="sxs-lookup"><span data-stu-id="f6992-p101">Sets and returns an [AllowNullsEnum](allownullsenum.md) value. The default value is **adIndexNullsDisallow**.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6992-108">备注</span><span class="sxs-lookup"><span data-stu-id="f6992-108">Remarks</span></span>

<span data-ttu-id="f6992-109">对于已追加到集合中的 [Index](index-object-adox.md) 对象，此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="f6992-109">This property is read-only on [Index](index-object-adox.md) objects already appended to a collection.</span></span>

