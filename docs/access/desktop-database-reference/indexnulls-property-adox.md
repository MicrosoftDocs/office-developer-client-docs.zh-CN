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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291474"
---
# <a name="indexnulls-property-adox"></a><span data-ttu-id="a2487-102">IndexNulls 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="a2487-102">IndexNulls property (ADOX)</span></span>


<span data-ttu-id="a2487-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a2487-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a2487-104">指示索引字段具有 null 值的记录是否有索引项。</span><span class="sxs-lookup"><span data-stu-id="a2487-104">Indicates whether records that have null values in their index fields have index entries.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="a2487-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="a2487-105">Settings and return values</span></span>

<span data-ttu-id="a2487-106">设置和返回一个 [AllowNullsEnum](allownullsenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="a2487-106">Sets and returns an [AllowNullsEnum](allownullsenum.md) value.</span></span> <span data-ttu-id="a2487-107">默认值为 **adIndexNullsDisallow**。</span><span class="sxs-lookup"><span data-stu-id="a2487-107">The default value is **adIndexNullsDisallow**.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2487-108">注解</span><span class="sxs-lookup"><span data-stu-id="a2487-108">Remarks</span></span>

<span data-ttu-id="a2487-109">对于已追加到集合中的 [Index](index-object-adox.md) 对象，此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="a2487-109">This property is read-only on [Index](index-object-adox.md) objects already appended to a collection.</span></span>

