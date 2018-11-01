---
title: IndexNulls 属性 (ADOX)
TOCTitle: IndexNulls Property (ADOX)
ms:assetid: 5c78c818-c23d-5b2c-d246-531aedc639df
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249326(v=office.15)
ms:contentKeyID: 48545089
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3458e6cc8ed6c1bc0a39c2e919c6ee272af4dafd
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877441"
---
# <a name="indexnulls-property-adox"></a><span data-ttu-id="f0218-102">IndexNulls 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="f0218-102">IndexNulls Property (ADOX)</span></span>


<span data-ttu-id="f0218-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f0218-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f0218-104">指示索引字段具有 null 值的记录是否有索引项。</span><span class="sxs-lookup"><span data-stu-id="f0218-104">Indicates whether records that have null values in their index fields have index entries.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="f0218-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="f0218-105">Settings and return values</span></span>

<span data-ttu-id="f0218-p101">设置和返回一个 [AllowNullsEnum](allownullsenum.md) 值。默认值为 **adIndexNullsDisallow** 。</span><span class="sxs-lookup"><span data-stu-id="f0218-p101">Sets and returns an [AllowNullsEnum](allownullsenum.md) value. The default value is **adIndexNullsDisallow**.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0218-108">备注</span><span class="sxs-lookup"><span data-stu-id="f0218-108">Remarks</span></span>

<span data-ttu-id="f0218-109">对于已追加到集合中的 [Index](index-object-adox.md) 对象，此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="f0218-109">This property is read-only on [Index](index-object-adox.md) objects already appended to a collection.</span></span>

