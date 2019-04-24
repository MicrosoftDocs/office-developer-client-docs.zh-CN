---
title: 编辑现有记录
TOCTitle: Editing existing records
ms:assetid: 86b961e0-e0a5-85a2-1138-7ab2e696ec11
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249585(v=office.15)
ms:contentKeyID: 48546089
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: dae80ddb85709ccc668e80adad0cb0c723c79cd5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293614"
---
# <a name="editing-existing-records"></a>编辑现有记录


**适用于**：Access 2013、Office 2013

若要编辑现有记录，请移动到希望编辑的行，并更改想更改的字段的 **Value** 属性。有关 **Field** 对象的 **Value** 属性的详细信息，请参阅 [第 3 章：检查数据](chapter-3-examining-data.md)。取决于游标类型，需要使用 **Update** 或 **UpdateBatch** 将更改发送回数据源。有关详细信息，请参阅 [第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)。

通常，更有效的方式是对命令对象使用存储过程来执行更新，同时执行其他操作，这是因为存储过程不需要创建游标。有关游标的详细信息，请参阅[第 8 章：了解游标和锁定](chapter-8-understanding-cursors-and-locks.md)。

