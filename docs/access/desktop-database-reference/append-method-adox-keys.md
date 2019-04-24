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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297086"
---
# <a name="append-method-adox-keys"></a><span data-ttu-id="0319d-102">Append 方法（ADOX 键）</span><span class="sxs-lookup"><span data-stu-id="0319d-102">Append method (ADOX Keys)</span></span>

<span data-ttu-id="0319d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0319d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0319d-104">将新的 [Key](key-object-adox.md) 对象添加到 [Keys](keys-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="0319d-104">Adds a new [Key](key-object-adox.md) object to the [Keys](keys-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="0319d-105">语法</span><span class="sxs-lookup"><span data-stu-id="0319d-105">Syntax</span></span>

<span data-ttu-id="0319d-106">*键*。Append*Key* \[、*KeyType* \] \[、\*\* \] Column \[、\*\* RelatedTable\] \*\* 、RelatedColumn \[\]</span><span class="sxs-lookup"><span data-stu-id="0319d-106">*Keys*.Append*Key* \[,*KeyType*\] \[,*Column*\] \[,*RelatedTable*\] \[,*RelatedColumn*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="0319d-107">参数</span><span class="sxs-lookup"><span data-stu-id="0319d-107">Parameters</span></span>

|<span data-ttu-id="0319d-108">参数</span><span class="sxs-lookup"><span data-stu-id="0319d-108">Parameter</span></span>|<span data-ttu-id="0319d-109">描述</span><span class="sxs-lookup"><span data-stu-id="0319d-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="0319d-110">*Key*</span><span class="sxs-lookup"><span data-stu-id="0319d-110">*Key*</span></span> |<span data-ttu-id="0319d-111">要追加的 **Key** 对象，或者要创建并追加的键的名称。</span><span class="sxs-lookup"><span data-stu-id="0319d-111">The **Key** object to append or the name of the key to create and append.</span></span>|
|<span data-ttu-id="0319d-112">*关键字*</span><span class="sxs-lookup"><span data-stu-id="0319d-112">*KeyType*</span></span> |<span data-ttu-id="0319d-113">可选。</span><span class="sxs-lookup"><span data-stu-id="0319d-113">Optional.</span></span> <span data-ttu-id="0319d-114">指定键类型的 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="0319d-114">A **Long** value that specifies the type of key.</span></span> <span data-ttu-id="0319d-115">*Key* 参数对应于 **Key** 对象的 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-keyadox) 属性。</span><span class="sxs-lookup"><span data-stu-id="0319d-115">The *Key* parameter corresponds to the [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-keyadox) property of a **Key** object.</span></span>|
|<span data-ttu-id="0319d-116">*列*</span><span class="sxs-lookup"><span data-stu-id="0319d-116">*Column*</span></span> |<span data-ttu-id="0319d-p102">可选。**String** 值，指定要进行索引的列的名称。*Columns* 参数对应于 [Column](column-object-adox.md) 对象的 [Name](name-property-adox.md) 属性值。</span><span class="sxs-lookup"><span data-stu-id="0319d-p102">Optional. A **String** value that specifies the name of the column to be indexed. The *Columns* parameter corresponds to the value of the [Name](name-property-adox.md) property of a [Column](column-object-adox.md) object.</span></span>|
|<span data-ttu-id="0319d-120">*RelatedTable*</span><span class="sxs-lookup"><span data-stu-id="0319d-120">*RelatedTable*</span></span> |<span data-ttu-id="0319d-p103">可选。指定相关表的名称的 **String** 值。*RelatedTable* 参数对应于 [Table](table-object-adox.md) 对象的 **Name** 属性值。</span><span class="sxs-lookup"><span data-stu-id="0319d-p103">Optional. A **String** value that specifies the name of the related table. The *RelatedTable* parameter corresponds to the value of the **Name** property of a [Table](table-object-adox.md) object.</span></span>|
|<span data-ttu-id="0319d-124">*RelatedColumn*</span><span class="sxs-lookup"><span data-stu-id="0319d-124">*RelatedColumn*</span></span> |<span data-ttu-id="0319d-p104">可选。 **String** 值，指定外键的相关列的名称。RelatedColumn 参数对应于 **Column** 对象的 **Name** 属性值。</span><span class="sxs-lookup"><span data-stu-id="0319d-p104">Optional. A **String** value that specifies the name of the related column for a foreign key. The RelatedColumn parameter corresponds to the value of the **Name** property of a **Column** object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0319d-128">注解</span><span class="sxs-lookup"><span data-stu-id="0319d-128">Remarks</span></span>

<span data-ttu-id="0319d-129">*Columns* 参数可接受列名或列名数组。</span><span class="sxs-lookup"><span data-stu-id="0319d-129">The *Columns* parameter can take either the name of a column or an array of column names.</span></span>

