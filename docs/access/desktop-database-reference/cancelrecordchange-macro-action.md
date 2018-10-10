---
title: CancelRecordChange 宏操作
TOCTitle: CancelRecordChange Macro Action
ms:assetid: 73031240-1ff6-660b-b25f-11a880df6031
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195846(v=office.15)
ms:contentKeyID: 48545626
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8fe474f9ba7250e3225bc73460c6d192800c861b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467052"
---
# <a name="cancelrecordchange-macro-action"></a>CancelRecordChange 宏操作


**适用于**： Access 2013 |Office 2013

使用 **CancelRecordChange** 操作可在提交更改之前取消在 **[CreateRecord](createrecord-data-block.md)** 或 **[EditRecord](editrecord-data-block.md)** 数据块中对某一记录应用的更改。


> [!NOTE]
> <P>[!注释] <STRONG>CancelRecordChange</STRONG> 操作仅适用于数据宏。</P>



## <a name="remarks"></a>注释

在调用 **CancelRecordChange** 操作时， **CreateRecord** 或 **EditRecord** 数据块将立即退出。

