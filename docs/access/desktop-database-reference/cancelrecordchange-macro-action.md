---
title: CancelRecordChange 宏操作
TOCTitle: CancelRecordChange macro action
ms:assetid: 73031240-1ff6-660b-b25f-11a880df6031
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195846(v=office.15)
ms:contentKeyID: 48545626
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d19e7adcdd3bb60f24d90e75942fcc0b4e16e2e2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296652"
---
# <a name="cancelrecordchange-macro-action"></a>CancelRecordChange 宏操作


**适用于**：Access 2013、Office 2013

使用 **CancelRecordChange** 操作可在提交更改之前取消在 **[CreateRecord](createrecord-data-block.md)** 或 **[EditRecord](editrecord-data-block.md)** 数据块中对某一记录应用的更改。


> [!NOTE]
> [!注释] **CancelRecordChange** 操作仅适用于数据宏。



## <a name="remarks"></a>注解

在调用 **CancelRecordChange** 操作时， **CreateRecord** 或 **EditRecord** 数据块将立即退出。

