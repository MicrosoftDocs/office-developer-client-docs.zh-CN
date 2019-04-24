---
title: Delete 方法 (ADOX 集合)
TOCTitle: Delete method (ADOX Collections)
ms:assetid: bcf9b8dd-cc7a-c1f9-fd93-58694766c4d9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249909(v=office.15)
ms:contentKeyID: 48547423
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 54c67848d321125af44d9f5bf50f3aa582b043bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294076"
---
# <a name="delete-method-adox-collections"></a><span data-ttu-id="4a549-102">Delete 方法 (ADOX 集合)</span><span class="sxs-lookup"><span data-stu-id="4a549-102">Delete method (ADOX Collections)</span></span>

<span data-ttu-id="4a549-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="4a549-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4a549-104">从集合中移除对象。</span><span class="sxs-lookup"><span data-stu-id="4a549-104">Removes an object from a collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a549-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a549-105">Syntax</span></span>

<span data-ttu-id="4a549-106">*集合*。删除*名称*</span><span class="sxs-lookup"><span data-stu-id="4a549-106">*Collection*.Delete*Name*</span></span>

## <a name="parameters"></a><span data-ttu-id="4a549-107">参数</span><span class="sxs-lookup"><span data-stu-id="4a549-107">Parameters</span></span>

|<span data-ttu-id="4a549-108">参数</span><span class="sxs-lookup"><span data-stu-id="4a549-108">Parameter</span></span>|<span data-ttu-id="4a549-109">描述</span><span class="sxs-lookup"><span data-stu-id="4a549-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="4a549-110">*Name*</span><span class="sxs-lookup"><span data-stu-id="4a549-110">*Name*</span></span> |<span data-ttu-id="4a549-111">一个 **Variant** 值，指定要删除的对象的名称或顺序位置（索引）。</span><span class="sxs-lookup"><span data-stu-id="4a549-111">A **Variant** that specifies the name or ordinal position (index) of the object to delete.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4a549-112">注解</span><span class="sxs-lookup"><span data-stu-id="4a549-112">Remarks</span></span>

<span data-ttu-id="4a549-113">如果集合中没有该 *Name*，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="4a549-113">An error will occur if the *Name* does not exist in the collection.</span></span>

<span data-ttu-id="4a549-p101">对于 [Tables](tables-collection-adox.md) 和 [Users](users-collection-adox.md) 集合，如果提供程序不支持删除表或用户，则会发生错误。对于 [Procedures](procedures-collection-adox.md) 和 [Views](views-collection-adox.md) 集合，如果提供程序不支持保留命令，则 **Delete** 将失败。</span><span class="sxs-lookup"><span data-stu-id="4a549-p101">For [Tables](tables-collection-adox.md) and [Users](users-collection-adox.md) collections, an error will occur if the provider does not support deleting tables or users, respectively. For [Procedures](procedures-collection-adox.md) and [Views](views-collection-adox.md) collections, **Delete** will fail if the provider does not support persisting commands.</span></span>

