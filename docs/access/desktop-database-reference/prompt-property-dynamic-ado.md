---
title: 提示动态属性 (ADO)
TOCTitle: Prompt dynamic property (ADO)
ms:assetid: 6c899b03-1d1f-a81f-dc17-7205a0230af9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249428(v=office.15)
ms:contentKeyID: 48545473
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 261ac5640b5239f27ad91e01d1cb23794f88740a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715184"
---
# <a name="prompt-dynamic-property-ado"></a><span data-ttu-id="38124-102">提示动态属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="38124-102">Prompt dynamic property (ADO)</span></span>

<span data-ttu-id="38124-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="38124-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="38124-104">指定 OLE DB 提供程序是否应当提示用户输入初始化信息。</span><span class="sxs-lookup"><span data-stu-id="38124-104">Specifies whether the OLE DB provider should prompt the user for initialization information.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="38124-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="38124-105">Settings and return values</span></span>

<span data-ttu-id="38124-106">设置和返回 [ConnectPromptEnum](connectpromptenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="38124-106">Sets and returns a [ConnectPromptEnum](connectpromptenum.md) value.</span></span>

## <a name="remarks"></a><span data-ttu-id="38124-107">备注</span><span class="sxs-lookup"><span data-stu-id="38124-107">Remarks</span></span>

<span data-ttu-id="38124-p101">**Prompt** 是一个动态属性，可以由 OLE DB 提供程序追加到 [Connection](connection-object-ado.md) 对象的 [Properties](properties-collection-ado.md) 集合中。若要提示初始化信息，OLE DB 提供程序通常会向用户显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="38124-p101">**Prompt** is a dynamic property, which may be appended to the [Connection](connection-object-ado.md) object's [Properties](properties-collection-ado.md) collection by the OLE DB provider. To prompt for initialization information, OLE DB providers will typically display a dialog box to the user.</span></span>

<span data-ttu-id="38124-p102">关闭 [Connection](connection-object-ado.md) 时， **Connection** 对象的动态属性将丢失。如果要使用默认值之外的其他值，则必须在重新打开 **Connection** 之前重新设置 **Prompt** 属性。</span><span class="sxs-lookup"><span data-stu-id="38124-p102">Dynamic properties of a [Connection](connection-object-ado.md) object are lost when the **Connection** is closed. The **Prompt** property must be reset before re-opening the **Connection** to use a value other than the default.</span></span>

> [!NOTE]
> <span data-ttu-id="38124-p103">[!注释] 不要指定提供程序应在用户无法响应对话框的情况下提示用户。例如，如果应用程序在服务器系统而不是用户客户端上运行，或者应用程序在没有用户登录的系统上运行，用户就无法进行响应。在这些情况下，应用程序将无限期地等待响应，从而表现为似乎已经锁定。</span><span class="sxs-lookup"><span data-stu-id="38124-p103">Do not specify that the provider should prompt the user in scenarios in which the user will not be able to respond to the dialog box. For example, the user will not be able to respond if the application is running on a server system instead of on the user's client, or if the application is running on a system with no user logged on. In these cases, the application will wait indefinitely for a response and seem to lock up.</span></span>

<span data-ttu-id="38124-115">**用法**</span><span class="sxs-lookup"><span data-stu-id="38124-115">**Usage**</span></span>

```vb
    Set cn = New Connection
    cn.Provider = "SQLOLEDB"
    cn.Properties("Prompt") = adPromptNever    ' do not prompt the user
```
