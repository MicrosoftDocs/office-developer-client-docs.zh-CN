---
title: Append 方法 (ADOX Columns)
TOCTitle: Append Method (ADOX Columns)
ms:assetid: e256a478-abc0-f15b-fc29-1b52e354144a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250152(v=office.15)
ms:contentKeyID: 48548285
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ec64241bf63719fe4f5c547d60a93f7804f181ca
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877658"
---
# <a name="append-method-adox-columns"></a><span data-ttu-id="61800-102">Append 方法 (ADOX Columns)</span><span class="sxs-lookup"><span data-stu-id="61800-102">Append Method (ADOX Columns)</span></span>


<span data-ttu-id="61800-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="61800-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="61800-104">将新的 [Column](column-object-adox.md) 对象添加到 [Columns](columns-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="61800-104">Adds a new [Column](column-object-adox.md) object to the [Columns](columns-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="61800-105">语法</span><span class="sxs-lookup"><span data-stu-id="61800-105">Syntax</span></span>

<span data-ttu-id="61800-106">*列*。</span><span class="sxs-lookup"><span data-stu-id="61800-106">*Columns*.</span></span> <span data-ttu-id="61800-107">追加*列* \[，*键入*\] \[，*DefinedSize*\]</span><span class="sxs-lookup"><span data-stu-id="61800-107">Append*Column* \[,*Type*\] \[,*DefinedSize*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="61800-108">参数</span><span class="sxs-lookup"><span data-stu-id="61800-108">Parameters</span></span>

  - <span data-ttu-id="61800-109">*Column*</span><span class="sxs-lookup"><span data-stu-id="61800-109">*Column*</span></span>

  - <span data-ttu-id="61800-110">要追加的 **Column** 对象，或者要创建并追加的列的名称。</span><span class="sxs-lookup"><span data-stu-id="61800-110">The **Column** object to append or the name of the column to create and append.</span></span>

  - <span data-ttu-id="61800-111">*Type*</span><span class="sxs-lookup"><span data-stu-id="61800-111">*Type*</span></span>

  - <span data-ttu-id="61800-112">可选。</span><span class="sxs-lookup"><span data-stu-id="61800-112">Optional.</span></span> <span data-ttu-id="61800-113">指定该列的数据类型的 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="61800-113">A **Long** value that specifies the data type of the column.</span></span> <span data-ttu-id="61800-114">*Type*参数对应于一个**Column**对象的[Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\))属性。</span><span class="sxs-lookup"><span data-stu-id="61800-114">The *Type* parameter corresponds to the [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) property of a **Column** object.</span></span>

  - <span data-ttu-id="61800-115">*DefinedSize*</span><span class="sxs-lookup"><span data-stu-id="61800-115">*DefinedSize*</span></span>

  - <span data-ttu-id="61800-116">可选。</span><span class="sxs-lookup"><span data-stu-id="61800-116">Optional.</span></span> <span data-ttu-id="61800-117">指定该列的大小的 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="61800-117">A **Long** value that specifies the size of the column.</span></span> <span data-ttu-id="61800-118">*DefinedSize*参数对应于一个**Column**对象的[DefinedSize](definedsize-property-adox.md)属性。</span><span class="sxs-lookup"><span data-stu-id="61800-118">The *DefinedSize* parameter corresponds to the [DefinedSize](definedsize-property-adox.md) property of a **Column** object.</span></span>


> [!NOTE]
> <span data-ttu-id="61800-119">[!注释] 如果追加到 **Tables** 集合中的 **Table** 中没有某个 [Column](index-object-adox.md) ，则在将该 **Column** 追加到 [Index](table-object-adox.md) 的 [Columns](tables-collection-adox.md) 集合时将发生错误。</span><span class="sxs-lookup"><span data-stu-id="61800-119">An error will occur when appending a **Column** to the **Columns** collection of an [Index](index-object-adox.md) if the **Column** does not exist in a [Table](table-object-adox.md) that is already appended to the [Tables](tables-collection-adox.md) collection.</span></span>


