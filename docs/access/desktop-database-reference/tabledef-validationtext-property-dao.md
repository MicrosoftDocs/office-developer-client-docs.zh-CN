---
title: TableDef.ValidationText Property (DAO)
TOCTitle: ValidationText Property
ms:assetid: 9f38616a-41ee-cbd1-9e29-da436b258e08
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198366(v=office.15)
ms:contentKeyID: 48546682
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1f41433d90703f230e50f3248103777ec3aba325
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876454"
---
# <a name="tabledefvalidationtext-property-dao"></a><span data-ttu-id="3bdd7-102">TableDef.ValidationText Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="3bdd7-102">TableDef.ValidationText Property (DAO)</span></span>


<span data-ttu-id="3bdd7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3bdd7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3bdd7-p101">设置或返回一个值，该值指定当 **Field** 对象的值不符合 **ValidationRule** 属性设置所指定的验证规则时应用程序显示的消息文本（仅适用于 Microsoft Access 工作区）。可读写 **String**。</span><span class="sxs-lookup"><span data-stu-id="3bdd7-p101">Sets or returns a value that specifies the text of the message that your application displays if the value of a **Field** object doesn't satisfy the validation rule specified by the **ValidationRule** property setting (Microsoft Access workspaces only). Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="3bdd7-106">语法</span><span class="sxs-lookup"><span data-stu-id="3bdd7-106">Syntax</span></span>

<span data-ttu-id="3bdd7-107">*表达式*。ValidationText</span><span class="sxs-lookup"><span data-stu-id="3bdd7-107">*expression* .ValidationText</span></span>

<span data-ttu-id="3bdd7-108">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="3bdd7-108">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="3bdd7-109">注解</span><span class="sxs-lookup"><span data-stu-id="3bdd7-109">Remarks</span></span>

<span data-ttu-id="3bdd7-110">在 **[TableDef](tabledef-object-dao.md)** 对象中，对于链接表，该属性设置是只读的，对于基表，该属性设置是可读写的。</span><span class="sxs-lookup"><span data-stu-id="3bdd7-110">For a **[TableDef](tabledef-object-dao.md)** object, this property setting is read-only for a linked table and read/write for a base table.</span></span>

