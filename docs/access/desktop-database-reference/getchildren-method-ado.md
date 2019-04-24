---
title: GetChildren 方法 (ADO)
TOCTitle: GetChildren method (ADO)
ms:assetid: 998cf640-ffc7-51e1-4d1e-4797f7cdea4a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249687(v=office.15)
ms:contentKeyID: 48546515
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4ca8c113a377543ea8624972adb5958612a3fc72
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292305"
---
# <a name="getchildren-method-ado"></a>GetChildren 方法 (ADO)


**适用于**：Access 2013、Office 2013


用于返回一个 [Recordset](recordset-object-ado.md)，该记录集的行代表 [Record](record-object-ado.md) 集合的子级。

## <a name="syntax"></a>语法

**Set***recordset* = *记录*。GetChildren

## <a name="return-value"></a>返回值

**Recordset** 对象，其每一行代表当前 **Record** 对象的一个子级。例如，代表目录的 **Record** 的子级应为包含在父目录中的文件和子目录。

## <a name="remarks"></a>注解

提供程序确定返回的 **Recordset** 中存在哪些列。例如，文档源提供程序始终返回一个资源 **Recordset**。

