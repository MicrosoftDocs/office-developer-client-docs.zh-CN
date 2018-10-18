---
title: GetChildren 方法 (ADO)
TOCTitle: GetChildren Method (ADO)
ms:assetid: 998cf640-ffc7-51e1-4d1e-4797f7cdea4a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249687(v=office.15)
ms:contentKeyID: 48546515
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 06474b6c4ecb29388367f8ceac7c7676002e1384
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25602655"
---
# <a name="getchildren-method-ado"></a>GetChildren 方法 (ADO)


**适用于**： Access 2013 |Office 2013


用于返回一个 [Recordset](recordset-object-ado.md)，该记录集的行代表 [Record](record-object-ado.md) 集合的子级。

## <a name="syntax"></a>语法

**设置***记录集* = *记录*。GetChildren

<<<<<<< 标头
## <a name="return-value"></a>返回值
=======
## <a name="return-value"></a>返回值
>>>>>>> master

**Recordset** 对象，其每一行代表当前 **Record** 对象的一个子级。例如，代表目录的 **Record** 的子级应为包含在父目录中的文件和子目录。

## <a name="remarks"></a>备注

提供程序确定返回的 **Recordset** 中存在哪些列。例如，文档源提供程序始终返回一个资源 **Recordset** 。

