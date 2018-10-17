---
title: TableDefs.Delete Method (DAO)
TOCTitle: Delete Method
ms:assetid: 130bb50d-17c3-b2ab-9360-0d91d0cee131
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845419(v=office.15)
ms:contentKeyID: 48543358
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e39a1390c9ea26baa83d8203967d603237a3ab1c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467221"
---
# <a name="tabledefsdelete-method-dao"></a><span data-ttu-id="1e588-102">TableDefs.Delete Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="1e588-102">TableDefs.Delete Method (DAO)</span></span>


<span data-ttu-id="1e588-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1e588-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1e588-104">从 **TableDefs** 集合中删除指定的 **TableDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="1e588-104">Deletes the specified **TableDef** object from the **TableDefs** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e588-105">语法</span><span class="sxs-lookup"><span data-stu-id="1e588-105">Syntax</span></span>

<span data-ttu-id="1e588-106">*表达式*。删除 （***名称***）</span><span class="sxs-lookup"><span data-stu-id="1e588-106">*expression* .Delete(***Name***)</span></span>

<span data-ttu-id="1e588-107">*表达式*一个代表**TableDefs**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="1e588-107">*expression* A variable that represents a **TableDefs** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="1e588-108">参数</span><span class="sxs-lookup"><span data-stu-id="1e588-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1e588-109">名称</span><span class="sxs-lookup"><span data-stu-id="1e588-109">Name</span></span></p></th>
<th><p><span data-ttu-id="1e588-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="1e588-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="1e588-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="1e588-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="1e588-112">说明</span><span class="sxs-lookup"><span data-stu-id="1e588-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e588-113">名称</span><span class="sxs-lookup"><span data-stu-id="1e588-113">Name</span></span></p></td>
<td><p><span data-ttu-id="1e588-114">必需</span><span class="sxs-lookup"><span data-stu-id="1e588-114">Required</span></span></p></td>
<td><p><span data-ttu-id="1e588-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="1e588-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="1e588-116">要删除的 TableDef 的名称。</span><span class="sxs-lookup"><span data-stu-id="1e588-116">The name of the TableDef to delete.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="1e588-117">注解</span><span class="sxs-lookup"><span data-stu-id="1e588-117">Remarks</span></span>

<span data-ttu-id="1e588-118">仅当**TableDef**对象的新且未被追加到数据库，或者**TableDef**的**可更新**属性设置为**True**时，才支持 Delete 方法。</span><span class="sxs-lookup"><span data-stu-id="1e588-118">The Delete method is supported only when the **TableDef** object is new and hasn’t been appended to the database, or when the **Updatable** property of the **TableDef** is set to **True**.</span></span>
