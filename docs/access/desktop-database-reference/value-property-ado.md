---
title: Value 属性 (ADO)
TOCTitle: Value Property (ADO)
ms:assetid: ff21d122-98e3-2b48-d92f-e696b8079fc5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250310(v=office.15)
ms:contentKeyID: 48548958
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 68c0d45345dfc768f5d435689abf67bcc3d9abe2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465762"
---
# <a name="value-property-ado"></a><span data-ttu-id="aea57-102">Value 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="aea57-102">Value Property (ADO)</span></span>


<span data-ttu-id="aea57-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="aea57-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="aea57-104">指示赋给 [Field](field-object-ado.md)、[Parameter](parameter-object-ado.md) 或 [Property](property-object-ado.md) 对象的值。</span><span class="sxs-lookup"><span data-stu-id="aea57-104">Indicates the value assigned to a [Field](field-object-ado.md), [Parameter](parameter-object-ado.md), or [Property](property-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="aea57-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="aea57-105">Settings and Return Values</span></span>

<span data-ttu-id="aea57-p101">设置或返回一个指示对象的值的 **Variant** 值。默认值取决于 [Type](type-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="aea57-p101">Sets or returns a **Variant** value that indicates the value of the object. Default value depends on the [Type](type-property-ado.md) property.</span></span>

## <a name="remarks"></a><span data-ttu-id="aea57-108">备注</span><span class="sxs-lookup"><span data-stu-id="aea57-108">Remarks</span></span>

<span data-ttu-id="aea57-p102">使用 **Value** 属性可以设置或返回来自 **Field** 对象的数据，设置或返回 **Parameter** 对象的参数值，或者设置或返回 **Property** 对象的属性设置。 **Value** 属性为可读/写还是只读属性取决于许多因素，有关详细信息，请参阅各个对象主题。</span><span class="sxs-lookup"><span data-stu-id="aea57-p102">Use the **Value** property to set or return data from **Field** objects, to set or return parameter values with **Parameter** objects, or to set or return property settings with **Property** objects. Whether the **Value** property is read/write or read-only depends upon numerous factors — see the respective object topics for more information.</span></span>

<span data-ttu-id="aea57-111">ADO 允许设置和返回 **Value** 属性的长二进制数据。</span><span class="sxs-lookup"><span data-stu-id="aea57-111">ADO allows setting and returning long binary data with the **Value** property.</span></span>


> [!NOTE]
> <P><span data-ttu-id="aea57-p103">[!注释] 对于 <STRONG>Parameter</STRONG> 对象，ADO 只从提供程序那里读取一次 <STRONG>Value</STRONG> 属性。如果某命令包含 <STRONG>Value</STRONG> 属性为空的 <STRONG>Parameter</STRONG> 并且将使用该命令来创建 <A href="recordset-object-ado.md">Recordset</A>，则请确保首先关闭 <STRONG>Recordset</STRONG> ，然后再检索 <STRONG>Value</STRONG> 属性。否则，对于某些提供程序， <STRONG>Value</STRONG> 属性可能为空，并且不包含正确的值。</span><span class="sxs-lookup"><span data-stu-id="aea57-p103">For <STRONG>Parameter</STRONG> objects, ADO reads the <STRONG>Value</STRONG> property only once from the provider. If a command contains a <STRONG>Parameter</STRONG> whose <STRONG>Value</STRONG> property is empty, and you create a <A href="recordset-object-ado.md">Recordset</A> from the command, ensure that you first close the <STRONG>Recordset</STRONG> before retrieving the <STRONG>Value</STRONG> property. Otherwise, for some providers, the <STRONG>Value</STRONG> property may be empty, and won't contain the correct value.</span></span></P>



<span data-ttu-id="aea57-p104">对于已追加到 **Record** 对象的 [Fields](fields-collection-ado.md) 集合中的新 [Field](record-object-ado.md) 对象，必须先设置 **Value** 属性，然后才能指定其他任何 **Field** 属性。首先，必须为 **Value** 属性赋予特定值，并对 [Fields](update-method-ado.md) 集合调用 **Update**。然后，可以访问诸如 [Type](type-property-ado.md) 或 [Attributes](attributes-property-ado.md) 等其他属性。</span><span class="sxs-lookup"><span data-stu-id="aea57-p104">For new **Field** objects that have been appended to the [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md) object, the **Value** property must be set before any other **Field** properties can be specified. First, a specific value for the **Value** property must have been assigned and [Update](update-method-ado.md) on the **Fields** collection called. Then, other properties such as [Type](type-property-ado.md) or [Attributes](attributes-property-ado.md) can be accessed.</span></span>
