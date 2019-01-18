---
title: Source 属性（ADO 错误）
TOCTitle: Source property (ADO Error)
ms:assetid: ffc6c77f-1494-d63a-d832-416faa4c6f07
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250316(v=office.15)
ms:contentKeyID: 48548969
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2f03dcc8049113df13ff8654aee340d1e2d6e502
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722891"
---
# <a name="source-property-ado-error"></a><span data-ttu-id="72dbd-102">Source 属性（ADO 错误）</span><span class="sxs-lookup"><span data-stu-id="72dbd-102">Source property (ADO Error)</span></span>


<span data-ttu-id="72dbd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="72dbd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="72dbd-104">指示最初生成错误的对象或应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="72dbd-104">Indicates the name of the object or application that originally generated an error.</span></span>

## <a name="return-value"></a><span data-ttu-id="72dbd-105">返回值</span><span class="sxs-lookup"><span data-stu-id="72dbd-105">Return value</span></span>

<span data-ttu-id="72dbd-106">返回一个 **String** 值，指示对象或应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="72dbd-106">Returns a **String** value that indicates the name of an object or application.</span></span>

## <a name="remarks"></a><span data-ttu-id="72dbd-107">备注</span><span class="sxs-lookup"><span data-stu-id="72dbd-107">Remarks</span></span>

<span data-ttu-id="72dbd-108">使用 **Error** 对象上的 [Source](error-object-ado.md) 属性可以确定生成错误的原始对象或应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="72dbd-108">Use the **Source** property on an [Error](error-object-ado.md) object to determine the name of the object or application that originally generated an error.</span></span> <span data-ttu-id="72dbd-109">这可以是对象的类名或编程 ID。</span><span class="sxs-lookup"><span data-stu-id="72dbd-109">This could be the object's class name or programmatic ID.</span></span> <span data-ttu-id="72dbd-110">对于在 ADO 中的错误，属性值将 \**ADODB。 \*\*\* ObjectName*，其中*ObjectName*是触发错误对象的名称。</span><span class="sxs-lookup"><span data-stu-id="72dbd-110">For errors in ADO, the property value will be \**ADODB.\*\*\*ObjectName*, where *ObjectName* is the name of the object that triggered the error.</span></span> <span data-ttu-id="72dbd-111">ADOX 和 ADO MD，则值将为 \**ADOX。 \*\*\* ObjectName*和 \**ADOMD。 \*\*\* ObjectName，* 分别。</span><span class="sxs-lookup"><span data-stu-id="72dbd-111">For ADOX and ADO MD, the value will be \**ADOX.\*\*\*ObjectName* and \**ADOMD.\*\*\*ObjectName,* respectively.</span></span>

<span data-ttu-id="72dbd-112">可以根据 **Error** 对象的 [Source](number-property-ado.md) 、 [Number](description-property-ado.md) 和 **Description** 属性的错误文档编写代码，以恰当地处理错误。</span><span class="sxs-lookup"><span data-stu-id="72dbd-112">Based on the error documentation from the **Source**, [Number](number-property-ado.md), and [Description](description-property-ado.md) properties of **Error** objects, you can write code that will handle the error appropriately.</span></span>

<span data-ttu-id="72dbd-113">对于 **Error** 对象， **Source** 属性为只读属性。</span><span class="sxs-lookup"><span data-stu-id="72dbd-113">The **Source** property is read-only for **Error** objects.</span></span>

