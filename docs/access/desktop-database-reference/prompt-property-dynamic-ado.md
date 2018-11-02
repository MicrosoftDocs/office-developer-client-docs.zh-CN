---
title: 提示动态属性 (ADO)
TOCTitle: Prompt dynamic property (ADO)
ms:assetid: 6c899b03-1d1f-a81f-dc17-7205a0230af9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249428(v=office.15)
ms:contentKeyID: 48545473
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1898169881042b9c7af36668e26c93200d0cb5f8
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924615"
---
# <a name="prompt-dynamic-property-ado"></a>提示动态属性 (ADO)


**适用于**： Access 2013、 Office 2013

指定 OLE DB 提供程序是否应当提示用户输入初始化信息。

## <a name="settings-and-return-values"></a>设置和返回值

设置和返回 [ConnectPromptEnum](connectpromptenum.md) 值。

## <a name="remarks"></a>备注

**Prompt** 是一个动态属性，可以由 OLE DB 提供程序追加到 [Connection](connection-object-ado.md) 对象的 [Properties](properties-collection-ado.md) 集合中。若要提示初始化信息，OLE DB 提供程序通常会向用户显示一个对话框。

关闭 [Connection](connection-object-ado.md) 时， **Connection** 对象的动态属性将丢失。如果要使用默认值之外的其他值，则必须在重新打开 **Connection** 之前重新设置 **Prompt** 属性。


> [!NOTE]
> <P>[!注释] 不要指定提供程序应在用户无法响应对话框的情况下提示用户。例如，如果应用程序在服务器系统而不是用户客户端上运行，或者应用程序在没有用户登录的系统上运行，用户就无法进行响应。在这些情况下，应用程序将无限期地等待响应，从而表现为似乎已经锁定。</P>



**用法**

```vb
    Set cn = New Connection
    cn.Provider = "SQLOLEDB"
    cn.Properties("Prompt") = adPromptNever    ' do not prompt the user
```
