---
title: Append 方法 (ADOX Columns)
TOCTitle: Append Method (ADOX Columns)
ms:assetid: e256a478-abc0-f15b-fc29-1b52e354144a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250152(v=office.15)
ms:contentKeyID: 48548285
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1f64f3b04df989348173ad2fc975dcefbd1114b2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465992"
---
# <a name="append-method-adox-columns"></a><span data-ttu-id="ca32d-102">Append 方法 (ADOX Columns)</span><span class="sxs-lookup"><span data-stu-id="ca32d-102">Append Method (ADOX Columns)</span></span>


<span data-ttu-id="ca32d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ca32d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ca32d-104">将新的 [Column](column-object-adox.md) 对象添加到 [Columns](columns-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="ca32d-104">Adds a new [Column](column-object-adox.md) object to the [Columns](columns-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="ca32d-105">语法</span><span class="sxs-lookup"><span data-stu-id="ca32d-105">Syntax</span></span>

<span data-ttu-id="ca32d-106">*列*。</span><span class="sxs-lookup"><span data-stu-id="ca32d-106">*Columns*.</span></span> <span data-ttu-id="ca32d-107">追加*列* \[，*键入*\] \[，*DefinedSize*\]</span><span class="sxs-lookup"><span data-stu-id="ca32d-107">Append*Column* \[,*Type*\] \[,*DefinedSize*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="ca32d-108">参数</span><span class="sxs-lookup"><span data-stu-id="ca32d-108">Parameters</span></span>

  - <span data-ttu-id="ca32d-109">*Column*</span><span class="sxs-lookup"><span data-stu-id="ca32d-109">*Column*</span></span>

  - <span data-ttu-id="ca32d-110">要追加的 **Column** 对象，或者要创建并追加的列的名称。</span><span class="sxs-lookup"><span data-stu-id="ca32d-110">The **Column** object to append or the name of the column to create and append.</span></span>

  - <span data-ttu-id="ca32d-111">*Type*</span><span class="sxs-lookup"><span data-stu-id="ca32d-111">*Type*</span></span>

  - <span data-ttu-id="ca32d-112">可选。</span><span class="sxs-lookup"><span data-stu-id="ca32d-112">Optional.</span></span> <span data-ttu-id="ca32d-113">指定该列的数据类型的 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="ca32d-113">A **Long** value that specifies the data type of the column.</span></span> <span data-ttu-id="ca32d-114">*Type*参数对应于一个**Column**对象的[Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\))属性。</span><span class="sxs-lookup"><span data-stu-id="ca32d-114">The *Type* parameter corresponds to the [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) property of a **Column** object.</span></span>

  - <span data-ttu-id="ca32d-115">*DefinedSize*</span><span class="sxs-lookup"><span data-stu-id="ca32d-115">*DefinedSize*</span></span>

  - <span data-ttu-id="ca32d-116">可选。</span><span class="sxs-lookup"><span data-stu-id="ca32d-116">Optional.</span></span> <span data-ttu-id="ca32d-117">指定该列的大小的 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="ca32d-117">A **Long** value that specifies the size of the column.</span></span> <span data-ttu-id="ca32d-118">*DefinedSize*参数对应于一个**Column**对象的[DefinedSize](definedsize-property-adox.md)属性。</span><span class="sxs-lookup"><span data-stu-id="ca32d-118">The *DefinedSize* parameter corresponds to the [DefinedSize](definedsize-property-adox.md) property of a **Column** object.</span></span>


> [!NOTE]
> <P><span data-ttu-id="ca32d-119">[!注释] 如果追加到 <STRONG>Tables</STRONG> 集合中的 <STRONG>Table</STRONG> 中没有某个 <A href="index-object-adox.md">Column</A> ，则在将该 <STRONG>Column</STRONG> 追加到 <A href="table-object-adox.md">Index</A> 的 <A href="tables-collection-adox.md">Columns</A> 集合时将发生错误。</span><span class="sxs-lookup"><span data-stu-id="ca32d-119">An error will occur when appending a <STRONG>Column</STRONG> to the <STRONG>Columns</STRONG> collection of an <A href="index-object-adox.md">Index</A> if the <STRONG>Column</STRONG> does not exist in a <A href="table-object-adox.md">Table</A> that is already appended to the <A href="tables-collection-adox.md">Tables</A> collection.</span></span></P>


