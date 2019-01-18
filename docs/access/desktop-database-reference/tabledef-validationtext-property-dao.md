---
title: TableDef.ValidationText 属性 (DAO)
TOCTitle: ValidationText Property
ms:assetid: 9f38616a-41ee-cbd1-9e29-da436b258e08
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198366(v=office.15)
ms:contentKeyID: 48546682
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f2c45aa1bd6f470b342ffec51f2affd39c7cb552
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710480"
---
# <a name="tabledefvalidationtext-property-dao"></a><span data-ttu-id="9a797-102">TableDef.ValidationText 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="9a797-102">TableDef.ValidationText property (DAO)</span></span>


<span data-ttu-id="9a797-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9a797-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9a797-p101">设置或返回一个值，该值指定当 **Field** 对象的值不符合 **ValidationRule** 属性设置所指定的验证规则时应用程序显示的消息文本（仅适用于 Microsoft Access 工作区）。可读写 **String**。</span><span class="sxs-lookup"><span data-stu-id="9a797-p101">Sets or returns a value that specifies the text of the message that your application displays if the value of a **Field** object doesn't satisfy the validation rule specified by the **ValidationRule** property setting (Microsoft Access workspaces only). Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="9a797-106">语法</span><span class="sxs-lookup"><span data-stu-id="9a797-106">Syntax</span></span>

<span data-ttu-id="9a797-107">*表达式*。ValidationText</span><span class="sxs-lookup"><span data-stu-id="9a797-107">*expression* .ValidationText</span></span>

<span data-ttu-id="9a797-108">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="9a797-108">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="9a797-109">注解</span><span class="sxs-lookup"><span data-stu-id="9a797-109">Remarks</span></span>

<span data-ttu-id="9a797-110">在 **[TableDef](tabledef-object-dao.md)** 对象中，对于链接表，该属性设置是只读的，对于基表，该属性设置是可读写的。</span><span class="sxs-lookup"><span data-stu-id="9a797-110">For a **[TableDef](tabledef-object-dao.md)** object, this property setting is read-only for a linked table and read/write for a base table.</span></span>

