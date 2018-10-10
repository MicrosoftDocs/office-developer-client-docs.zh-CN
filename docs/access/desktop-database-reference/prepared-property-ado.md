---
title: Prepared 属性 (ADO)
TOCTitle: Prepared Property (ADO)
ms:assetid: 33becda2-faab-5000-8904-6ffd8c5805f2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249105(v=office.15)
ms:contentKeyID: 48544116
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231161
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 865453f89cd5942ec7f9f8d036beb72dc519397e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465809"
---
# <a name="prepared-property-ado"></a>Prepared 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示是否在执行之前保存命令的已编译版本。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Boolean** 值，如果设置为 **True** ，则指示应先准备命令。

## <a name="remarks"></a>备注

使用 **Prepared** 属性可使提供程序在首次执行 [Command](commandtext-property-ado.md) 对象之前保存 [CommandText](command-object-ado.md) 属性中指定查询的准备（或已编译）版本。这会降低命令首次执行的速度，但是提供程序一旦编译了命令，在以后执行该命令时提供程序将使用其已编译版本，这样可提高性能。

如果该属性为 **False** ，则提供程序将直接执行 **Command** 对象，而不创建已编译版本。

如果提供程序不支持命令准备功能，则此属性设置为 **True** 时会立刻返回错误。如果没有返回错误，则会直接忽略准备命令的请求，并将 **Prepared** 属性设置为 **False** 。

