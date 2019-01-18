---
title: Append 方法（ADOX 列）
TOCTitle: Append method (ADOX Columns)
ms:assetid: e256a478-abc0-f15b-fc29-1b52e354144a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250152(v=office.15)
ms:contentKeyID: 48548285
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 48bc100b7b56265a570ce963b80f569f1d827150
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711229"
---
# <a name="append-method-adox-columns"></a><span data-ttu-id="b8a9a-102">Append 方法（ADOX 列）</span><span class="sxs-lookup"><span data-stu-id="b8a9a-102">Append method (ADOX Columns)</span></span>

<span data-ttu-id="b8a9a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b8a9a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b8a9a-104">将新的 [Column](column-object-adox.md) 对象添加到 [Columns](columns-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="b8a9a-104">Adds a new [Column](column-object-adox.md) object to the [Columns](columns-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8a9a-105">语法</span><span class="sxs-lookup"><span data-stu-id="b8a9a-105">Syntax</span></span>

<span data-ttu-id="b8a9a-106">*列*。</span><span class="sxs-lookup"><span data-stu-id="b8a9a-106">*Columns*.</span></span> <span data-ttu-id="b8a9a-107">追加*列* \[，*键入*\] \[，*DefinedSize*\]</span><span class="sxs-lookup"><span data-stu-id="b8a9a-107">Append*Column* \[,*Type*\] \[,*DefinedSize*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="b8a9a-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="b8a9a-108">Parameters</span></span>

|<span data-ttu-id="b8a9a-109">参数</span><span class="sxs-lookup"><span data-stu-id="b8a9a-109">Parameter</span></span>|<span data-ttu-id="b8a9a-110">说明</span><span class="sxs-lookup"><span data-stu-id="b8a9a-110">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="b8a9a-111">*Column*</span><span class="sxs-lookup"><span data-stu-id="b8a9a-111">*Column*</span></span> |<span data-ttu-id="b8a9a-112">要追加的 **Column** 对象，或者要创建并追加的列的名称。</span><span class="sxs-lookup"><span data-stu-id="b8a9a-112">The **Column** object to append or the name of the column to create and append.</span></span>|
|<span data-ttu-id="b8a9a-113">*Type*</span><span class="sxs-lookup"><span data-stu-id="b8a9a-113">*Type*</span></span> |<span data-ttu-id="b8a9a-114">可选。</span><span class="sxs-lookup"><span data-stu-id="b8a9a-114">Optional.</span></span> <span data-ttu-id="b8a9a-115">指定该列的数据类型的 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="b8a9a-115">A **Long** value that specifies the data type of the column.</span></span> <span data-ttu-id="b8a9a-116">*Type*参数对应于一个**Column**对象的[Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox)属性。</span><span class="sxs-lookup"><span data-stu-id="b8a9a-116">The *Type* parameter corresponds to the [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) property of a **Column** object.</span></span>|
|<span data-ttu-id="b8a9a-117">*DefinedSize*</span><span class="sxs-lookup"><span data-stu-id="b8a9a-117">*DefinedSize*</span></span> |<span data-ttu-id="b8a9a-118">可选。</span><span class="sxs-lookup"><span data-stu-id="b8a9a-118">Optional.</span></span> <span data-ttu-id="b8a9a-119">指定该列的大小的 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="b8a9a-119">A **Long** value that specifies the size of the column.</span></span> <span data-ttu-id="b8a9a-120">*DefinedSize*参数对应于一个**Column**对象的[DefinedSize](definedsize-property-adox.md)属性。</span><span class="sxs-lookup"><span data-stu-id="b8a9a-120">The *DefinedSize* parameter corresponds to the [DefinedSize](definedsize-property-adox.md) property of a **Column** object.</span></span>|


> [!NOTE]
> <span data-ttu-id="b8a9a-121">[!注释] 如果追加到 **Tables** 集合中的 **Table** 中没有某个 [Column](index-object-adox.md) ，则在将该 **Column** 追加到 [Index](table-object-adox.md) 的 [Columns](tables-collection-adox.md) 集合时将发生错误。</span><span class="sxs-lookup"><span data-stu-id="b8a9a-121">An error will occur when appending a **Column** to the **Columns** collection of an [Index](index-object-adox.md) if the **Column** does not exist in a [Table](table-object-adox.md) that is already appended to the [Tables](tables-collection-adox.md) collection.</span></span>


