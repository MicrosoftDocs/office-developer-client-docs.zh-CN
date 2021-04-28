---
title: Source 属性（ADO 错误）
TOCTitle: Source property (ADO Error)
ms:assetid: ffc6c77f-1494-d63a-d832-416faa4c6f07
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250316(v=office.15)
ms:contentKeyID: 48548969
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 47ae7ea790265edc10be8c907869eefbe4e593ba
ms.sourcegitcommit: 66e74e39f44dca8c41f97f05528b8f9eb1aaed87
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061305"
---
# <a name="source-property-ado-error"></a><span data-ttu-id="0726e-102">Source 属性（ADO 错误）</span><span class="sxs-lookup"><span data-stu-id="0726e-102">Source property (ADO Error)</span></span>


<span data-ttu-id="0726e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0726e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0726e-104">指示最初生成错误的对象或应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="0726e-104">Indicates the name of the object or application that originally generated an error.</span></span>

## <a name="return-value"></a><span data-ttu-id="0726e-105">返回值</span><span class="sxs-lookup"><span data-stu-id="0726e-105">Return value</span></span>

<span data-ttu-id="0726e-106">返回一个 **String** 值，指示对象或应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="0726e-106">Returns a **String** value that indicates the name of an object or application.</span></span>

## <a name="remarks"></a><span data-ttu-id="0726e-107">备注</span><span class="sxs-lookup"><span data-stu-id="0726e-107">Remarks</span></span>

<span data-ttu-id="0726e-108">使用 [Error](error-object-ado.md) 对象上的 **Source** 属性可以确定生成错误的原始对象或应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="0726e-108">Use the **Source** property on an [Error](error-object-ado.md) object to determine the name of the object or application that originally generated an error.</span></span> <span data-ttu-id="0726e-109">这可以是对象的类名或编程 ID。</span><span class="sxs-lookup"><span data-stu-id="0726e-109">This could be the object's class name or programmatic ID.</span></span> <span data-ttu-id="0726e-110">对于 ADO 中的错误，该属性值将为 **ADODB.**</span><span class="sxs-lookup"><span data-stu-id="0726e-110">For errors in ADO, the property value will be **ADODB.**</span></span> <span data-ttu-id="0726e-111">*ObjectName*，其中 *ObjectName* 是触发错误的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="0726e-111">*ObjectName*, where *ObjectName* is the name of the object that triggered the error.</span></span> <span data-ttu-id="0726e-112">对于 ADOX 和 ADO MD，该值将分别为 **ADOX.**</span><span class="sxs-lookup"><span data-stu-id="0726e-112">For ADOX and ADO MD, the value will be **ADOX.**</span></span> <span data-ttu-id="0726e-113">*ObjectName* 和 **ADOMD.**</span><span class="sxs-lookup"><span data-stu-id="0726e-113">*ObjectName* and **ADOMD.**</span></span> <span data-ttu-id="0726e-114">*ObjectName*。</span><span class="sxs-lookup"><span data-stu-id="0726e-114">*ObjectName,* respectively.</span></span>

<span data-ttu-id="0726e-115">可以根据 **Error** 对象的 **Source**、[Number](number-property-ado.md) 和 [Description](description-property-ado.md) 属性的错误文档编写代码，以恰当地处理错误。</span><span class="sxs-lookup"><span data-stu-id="0726e-115">Based on the error documentation from the **Source**, [Number](number-property-ado.md), and [Description](description-property-ado.md) properties of **Error** objects, you can write code that will handle the error appropriately.</span></span>

<span data-ttu-id="0726e-116">对于 **Error** 对象，**Source** 属性为只读属性。</span><span class="sxs-lookup"><span data-stu-id="0726e-116">The **Source** property is read-only for **Error** objects.</span></span>

