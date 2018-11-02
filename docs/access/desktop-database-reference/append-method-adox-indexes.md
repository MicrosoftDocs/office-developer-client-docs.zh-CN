---
title: Append 方法（ADOX 索引）
TOCTitle: Append method (ADOX Indexes)
ms:assetid: 015ebab4-5e9d-8777-ac82-4d20e957c274
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248784(v=office.15)
ms:contentKeyID: 48542933
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 41eb1cc67dd5a2058f9c5673db381f0bc9067454
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921478"
---
# <a name="append-method-adox-indexes"></a><span data-ttu-id="cfb9b-102">Append 方法（ADOX 索引）</span><span class="sxs-lookup"><span data-stu-id="cfb9b-102">Append method (ADOX Indexes)</span></span>


<span data-ttu-id="cfb9b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cfb9b-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="cfb9b-104">将新的 [Index](index-object-adox.md) 对象添加到 [Indexes](indexes-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="cfb9b-104">Adds a new [Index](index-object-adox.md) object to the [Indexes](indexes-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="cfb9b-105">语法</span><span class="sxs-lookup"><span data-stu-id="cfb9b-105">Syntax</span></span>

<span data-ttu-id="cfb9b-106">*索引*。追加*索引* \[，*列*\]</span><span class="sxs-lookup"><span data-stu-id="cfb9b-106">*Indexes*.Append*Index* \[,*Columns*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="cfb9b-107">参数</span><span class="sxs-lookup"><span data-stu-id="cfb9b-107">Parameters</span></span>

  - <span data-ttu-id="cfb9b-108">*Index*</span><span class="sxs-lookup"><span data-stu-id="cfb9b-108">*Index*</span></span>

  - <span data-ttu-id="cfb9b-109">要追加的 **Index** 对象，或者要创建并追加的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="cfb9b-109">The **Index** object to append or the name of the index to create and append.</span></span>

  - <span data-ttu-id="cfb9b-110">*Columns*</span><span class="sxs-lookup"><span data-stu-id="cfb9b-110">*Columns*</span></span>

  - <span data-ttu-id="cfb9b-111">可选。</span><span class="sxs-lookup"><span data-stu-id="cfb9b-111">Optional.</span></span> <span data-ttu-id="cfb9b-112">一个 **Variant** 值，指定要进行索引的列的名称。</span><span class="sxs-lookup"><span data-stu-id="cfb9b-112">A **Variant** value that specifies the name(s) of the column(s) to be indexed.</span></span> <span data-ttu-id="cfb9b-113">*Columns*参数对应于一个[Column](column-object-adox.md)对象或对象的[Name](name-property-adox.md)属性的值。</span><span class="sxs-lookup"><span data-stu-id="cfb9b-113">The *Columns* parameter corresponds to the value(s) of the [Name](name-property-adox.md) property of a [Column](column-object-adox.md) object or objects.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfb9b-114">说明</span><span class="sxs-lookup"><span data-stu-id="cfb9b-114">Remarks</span></span>

<span data-ttu-id="cfb9b-115">*Columns*参数可接受的列的名称或列名的数组。</span><span class="sxs-lookup"><span data-stu-id="cfb9b-115">The *Columns* parameter can take either the name of a column or an array of column names.</span></span>

<span data-ttu-id="cfb9b-116">如果提供程序不支持创建索引，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="cfb9b-116">An error will occur if the provider does not support creating indexes.</span></span>

