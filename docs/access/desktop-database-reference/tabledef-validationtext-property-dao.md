---
title: TableDef.ValidationText 属性 (DAO)
TOCTitle: ValidationText Property
ms:assetid: 9f38616a-41ee-cbd1-9e29-da436b258e08
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198366(v=office.15)
ms:contentKeyID: 48546682
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b90c2fe3d27dea2f90261cda66e0cd0460349482
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921906"
---
# <a name="tabledefvalidationtext-property-dao"></a><span data-ttu-id="26cb6-102">TableDef.ValidationText 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="26cb6-102">TableDef.ValidationText property (DAO)</span></span>


<span data-ttu-id="26cb6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="26cb6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="26cb6-p101">设置或返回一个值，该值指定当 **Field** 对象的值不符合 **ValidationRule** 属性设置所指定的验证规则时应用程序显示的消息文本（仅适用于 Microsoft Access 工作区）。可读写 **String**。</span><span class="sxs-lookup"><span data-stu-id="26cb6-p101">Sets or returns a value that specifies the text of the message that your application displays if the value of a **Field** object doesn't satisfy the validation rule specified by the **ValidationRule** property setting (Microsoft Access workspaces only). Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="26cb6-106">语法</span><span class="sxs-lookup"><span data-stu-id="26cb6-106">Syntax</span></span>

<span data-ttu-id="26cb6-107">*表达式*。ValidationText</span><span class="sxs-lookup"><span data-stu-id="26cb6-107">*expression* .ValidationText</span></span>

<span data-ttu-id="26cb6-108">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="26cb6-108">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="26cb6-109">注解</span><span class="sxs-lookup"><span data-stu-id="26cb6-109">Remarks</span></span>

<span data-ttu-id="26cb6-110">在 **[TableDef](tabledef-object-dao.md)** 对象中，对于链接表，该属性设置是只读的，对于基表，该属性设置是可读写的。</span><span class="sxs-lookup"><span data-stu-id="26cb6-110">For a **[TableDef](tabledef-object-dao.md)** object, this property setting is read-only for a linked table and read/write for a base table.</span></span>

