---
title: Append 方法（ADOX 索引）
TOCTitle: Append method (ADOX Indexes)
ms:assetid: 015ebab4-5e9d-8777-ac82-4d20e957c274
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248784(v=office.15)
ms:contentKeyID: 48542933
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0b541512de9748e94d033bb56f27dd0941c7f5a7
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707554"
---
# <a name="append-method-adox-indexes"></a><span data-ttu-id="6b4cc-102">Append 方法（ADOX 索引）</span><span class="sxs-lookup"><span data-stu-id="6b4cc-102">Append method (ADOX Indexes)</span></span>


<span data-ttu-id="6b4cc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6b4cc-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="6b4cc-104">将新的 [Index](index-object-adox.md) 对象添加到 [Indexes](indexes-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="6b4cc-104">Adds a new [Index](index-object-adox.md) object to the [Indexes](indexes-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b4cc-105">语法</span><span class="sxs-lookup"><span data-stu-id="6b4cc-105">Syntax</span></span>

<span data-ttu-id="6b4cc-106">*索引*。追加*索引* \[，*列*\]</span><span class="sxs-lookup"><span data-stu-id="6b4cc-106">*Indexes*.Append*Index* \[,*Columns*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="6b4cc-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="6b4cc-107">Parameters</span></span>

|<span data-ttu-id="6b4cc-108">参数</span><span class="sxs-lookup"><span data-stu-id="6b4cc-108">Parameter</span></span>|<span data-ttu-id="6b4cc-109">说明</span><span class="sxs-lookup"><span data-stu-id="6b4cc-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="6b4cc-110">*Index*</span><span class="sxs-lookup"><span data-stu-id="6b4cc-110">*Index*</span></span> |<span data-ttu-id="6b4cc-111">要追加的 **Index** 对象，或者要创建并追加的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="6b4cc-111">The **Index** object to append or the name of the index to create and append.</span></span>|
|<span data-ttu-id="6b4cc-112">*Columns*</span><span class="sxs-lookup"><span data-stu-id="6b4cc-112">*Columns*</span></span> |<span data-ttu-id="6b4cc-113">可选。</span><span class="sxs-lookup"><span data-stu-id="6b4cc-113">Optional.</span></span> <span data-ttu-id="6b4cc-114">一个 **Variant** 值，指定要进行索引的列的名称。</span><span class="sxs-lookup"><span data-stu-id="6b4cc-114">A **Variant** value that specifies the name(s) of the column(s) to be indexed.</span></span> <span data-ttu-id="6b4cc-115">*Columns*参数对应于一个[Column](column-object-adox.md)对象或对象的[Name](name-property-adox.md)属性的值。</span><span class="sxs-lookup"><span data-stu-id="6b4cc-115">The *Columns* parameter corresponds to the value(s) of the [Name](name-property-adox.md) property of a [Column](column-object-adox.md) object or objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6b4cc-116">备注</span><span class="sxs-lookup"><span data-stu-id="6b4cc-116">Remarks</span></span>

<span data-ttu-id="6b4cc-117">*Columns*参数可接受的列的名称或列名的数组。</span><span class="sxs-lookup"><span data-stu-id="6b4cc-117">The *Columns* parameter can take either the name of a column or an array of column names.</span></span>

<span data-ttu-id="6b4cc-118">如果提供程序不支持创建索引，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="6b4cc-118">An error will occur if the provider does not support creating indexes.</span></span>

