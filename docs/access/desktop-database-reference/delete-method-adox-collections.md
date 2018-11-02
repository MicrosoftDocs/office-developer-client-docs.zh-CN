---
title: Delete 方法 （ADOX 集合）
TOCTitle: Delete method (ADOX Collections)
ms:assetid: bcf9b8dd-cc7a-c1f9-fd93-58694766c4d9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249909(v=office.15)
ms:contentKeyID: 48547423
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b5fdcd80a49d7d9d14ba17a85f675fdfd9906c1b
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921661"
---
# <a name="delete-method-adox-collections"></a><span data-ttu-id="4bd84-102">Delete 方法 （ADOX 集合）</span><span class="sxs-lookup"><span data-stu-id="4bd84-102">Delete method (ADOX Collections)</span></span>


<span data-ttu-id="4bd84-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4bd84-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="4bd84-104">从集合中移除对象。</span><span class="sxs-lookup"><span data-stu-id="4bd84-104">Removes an object from a collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="4bd84-105">语法</span><span class="sxs-lookup"><span data-stu-id="4bd84-105">Syntax</span></span>

<span data-ttu-id="4bd84-106">*集合*。删除*名称*</span><span class="sxs-lookup"><span data-stu-id="4bd84-106">*Collection*.Delete*Name*</span></span>

## <a name="parameters"></a><span data-ttu-id="4bd84-107">参数</span><span class="sxs-lookup"><span data-stu-id="4bd84-107">Parameters</span></span>

  - <span data-ttu-id="4bd84-108">*Name*</span><span class="sxs-lookup"><span data-stu-id="4bd84-108">*Name*</span></span>

  - <span data-ttu-id="4bd84-109">一个 **Variant** 值，指定要删除的对象的名称或顺序位置（索引）。</span><span class="sxs-lookup"><span data-stu-id="4bd84-109">A **Variant** that specifies the name or ordinal position (index) of the object to delete.</span></span>

## <a name="remarks"></a><span data-ttu-id="4bd84-110">备注</span><span class="sxs-lookup"><span data-stu-id="4bd84-110">Remarks</span></span>

<span data-ttu-id="4bd84-111">如果*名称*不存在集合中，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="4bd84-111">An error will occur if the *Name* does not exist in the collection.</span></span>

<span data-ttu-id="4bd84-p101">对于 [Tables](tables-collection-adox.md) 和 [Users](users-collection-adox.md) 集合，如果提供程序不支持删除表或用户，则会发生错误。对于 [Procedures](procedures-collection-adox.md) 和 [Views](views-collection-adox.md) 集合，如果提供程序不支持保留命令，则 **Delete** 将失败。</span><span class="sxs-lookup"><span data-stu-id="4bd84-p101">For [Tables](tables-collection-adox.md) and [Users](users-collection-adox.md) collections, an error will occur if the provider does not support deleting tables or users, respectively. For [Procedures](procedures-collection-adox.md) and [Views](views-collection-adox.md) collections, **Delete** will fail if the provider does not support persisting commands.</span></span>

