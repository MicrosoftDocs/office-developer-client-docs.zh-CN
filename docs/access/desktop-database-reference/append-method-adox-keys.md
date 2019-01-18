---
title: Append 方法（ADOX 键）
TOCTitle: Append method (ADOX Keys)
ms:assetid: 14d6e8d7-5c9e-a422-47d6-ebfd9dd7a120
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248913(v=office.15)
ms:contentKeyID: 48543396
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c301f6809ab7f785497637b12e0b5d7a0bb7772d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718901"
---
# <a name="append-method-adox-keys"></a><span data-ttu-id="72678-102">Append 方法（ADOX 键）</span><span class="sxs-lookup"><span data-stu-id="72678-102">Append method (ADOX Keys)</span></span>

<span data-ttu-id="72678-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="72678-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="72678-104">将新的 [Key](key-object-adox.md) 对象添加到 [Keys](keys-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="72678-104">Adds a new [Key](key-object-adox.md) object to the [Keys](keys-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="72678-105">语法</span><span class="sxs-lookup"><span data-stu-id="72678-105">Syntax</span></span>

<span data-ttu-id="72678-106">*键*。追加*密钥* \[，*关键字类型*\] \[，*列*\] \[，*RelatedTable* \] \[，*RelatedColumn*\]</span><span class="sxs-lookup"><span data-stu-id="72678-106">*Keys*.Append*Key* \[,*KeyType*\] \[,*Column*\] \[,*RelatedTable*\] \[,*RelatedColumn*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="72678-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="72678-107">Parameters</span></span>

|<span data-ttu-id="72678-108">参数</span><span class="sxs-lookup"><span data-stu-id="72678-108">Parameter</span></span>|<span data-ttu-id="72678-109">说明</span><span class="sxs-lookup"><span data-stu-id="72678-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="72678-110">*Key*</span><span class="sxs-lookup"><span data-stu-id="72678-110">*Key*</span></span> |<span data-ttu-id="72678-111">要追加的 **Key** 对象，或者要创建并追加的键的名称。</span><span class="sxs-lookup"><span data-stu-id="72678-111">The **Key** object to append or the name of the key to create and append.</span></span>|
|<span data-ttu-id="72678-112">*关键字类型*</span><span class="sxs-lookup"><span data-stu-id="72678-112">*KeyType*</span></span> |<span data-ttu-id="72678-113">可选。</span><span class="sxs-lookup"><span data-stu-id="72678-113">Optional.</span></span> <span data-ttu-id="72678-114">指定键类型的 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="72678-114">A **Long** value that specifies the type of key.</span></span> <span data-ttu-id="72678-115">*Key*参数对应于**Key**对象的[Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-keyadox)属性。</span><span class="sxs-lookup"><span data-stu-id="72678-115">The *Key* parameter corresponds to the [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-keyadox) property of a **Key** object.</span></span>|
|<span data-ttu-id="72678-116">*Column*</span><span class="sxs-lookup"><span data-stu-id="72678-116">*Column*</span></span> |<span data-ttu-id="72678-117">可选。</span><span class="sxs-lookup"><span data-stu-id="72678-117">Optional.</span></span> <span data-ttu-id="72678-118">**String** 值，指定要进行索引的列的名称。</span><span class="sxs-lookup"><span data-stu-id="72678-118">A **String** value that specifies the name of the column to be indexed.</span></span> <span data-ttu-id="72678-119">*Columns*参数对应于一个[Column](column-object-adox.md)对象的[Name](name-property-adox.md)属性的值。</span><span class="sxs-lookup"><span data-stu-id="72678-119">The *Columns* parameter corresponds to the value of the [Name](name-property-adox.md) property of a [Column](column-object-adox.md) object.</span></span>|
|<span data-ttu-id="72678-120">*RelatedTable*</span><span class="sxs-lookup"><span data-stu-id="72678-120">*RelatedTable*</span></span> |<span data-ttu-id="72678-121">可选。</span><span class="sxs-lookup"><span data-stu-id="72678-121">Optional.</span></span> <span data-ttu-id="72678-122">指定相关表的名称的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="72678-122">A **String** value that specifies the name of the related table.</span></span> <span data-ttu-id="72678-123">*RelatedTable*参数对应于一个[Table](table-object-adox.md)对象的**Name**属性的值。</span><span class="sxs-lookup"><span data-stu-id="72678-123">The *RelatedTable* parameter corresponds to the value of the **Name** property of a [Table](table-object-adox.md) object.</span></span>|
|<span data-ttu-id="72678-124">*RelatedColumn*</span><span class="sxs-lookup"><span data-stu-id="72678-124">*RelatedColumn*</span></span> |<span data-ttu-id="72678-p104">可选。 **String** 值，指定外键的相关列的名称。RelatedColumn 参数对应于 **Column** 对象的 **Name** 属性值。</span><span class="sxs-lookup"><span data-stu-id="72678-p104">Optional. A **String** value that specifies the name of the related column for a foreign key. The RelatedColumn parameter corresponds to the value of the **Name** property of a **Column** object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="72678-128">备注</span><span class="sxs-lookup"><span data-stu-id="72678-128">Remarks</span></span>

<span data-ttu-id="72678-129">*Columns*参数可接受的列的名称或列名的数组。</span><span class="sxs-lookup"><span data-stu-id="72678-129">The *Columns* parameter can take either the name of a column or an array of column names.</span></span>

