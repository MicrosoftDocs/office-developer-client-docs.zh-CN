---
title: Direction 属性 (ADO)
TOCTitle: Direction property (ADO)
ms:assetid: 51a94abb-7ce9-9adb-2b76-5391eb9f6863
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249262(v=office.15)
ms:contentKeyID: 48544823
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b9e34522a69b2e79f8ef44b912e2c0648c5b813d
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881291"
---
# <a name="direction-property-ado"></a><span data-ttu-id="362a5-102">Direction 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="362a5-102">Direction property (ADO)</span></span>


<span data-ttu-id="362a5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="362a5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="362a5-104">指示 [Parameter](parameter-object-ado.md) 参数是表示输入参数、输出参数还是输入输出参数，或者该参数是否为某个存储过程的返回值。</span><span class="sxs-lookup"><span data-stu-id="362a5-104">Indicates whether the [Parameter](parameter-object-ado.md) represents an input parameter, an output parameter, an input and an output parameter, or if the parameter is the return value from a stored procedure.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="362a5-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="362a5-105">Settings and return values</span></span>

<span data-ttu-id="362a5-106">设置或返回 [ParameterDirectionEnum](parameterdirectionenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="362a5-106">Sets or returns a [ParameterDirectionEnum](parameterdirectionenum.md) value.</span></span>

## <a name="remarks"></a><span data-ttu-id="362a5-107">备注</span><span class="sxs-lookup"><span data-stu-id="362a5-107">Remarks</span></span>

<span data-ttu-id="362a5-p101">使用 **Direction** 属性可以指定如何向过程或从过程传递参数。 **Direction** 属性为读/写属性；这样就可以使用不会返回此信息的提供程序，或者在不希望 ADO 对提供程序进行额外调用来检索参数信息的情况下设置此信息。</span><span class="sxs-lookup"><span data-stu-id="362a5-p101">Use the **Direction** property to specify how a parameter is passed to or from a procedure. The **Direction** property is read/write; this allows you to work with providers that don't return this information or to set this information when you don't want ADO to make an extra call to the provider to retrieve parameter information.</span></span>

<span data-ttu-id="362a5-p102">并非所有提供程序都可以确定其存储过程中的参数传递方向。在这种情况下，必须在执行查询前设置 **Direction** 属性。</span><span class="sxs-lookup"><span data-stu-id="362a5-p102">Not all providers can determine the direction of parameters in their stored procedures. In these cases, you must set the **Direction** property before you execute the query.</span></span>

