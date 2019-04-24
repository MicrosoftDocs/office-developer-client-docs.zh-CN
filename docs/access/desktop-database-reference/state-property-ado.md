---
title: State 属性 (ADO)
TOCTitle: State property (ADO)
ms:assetid: ade0a50c-e2d8-23ac-4ea9-b012fedcd5db
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249819(v=office.15)
ms:contentKeyID: 48547053
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231176
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 0bce3f87a6530315a128396fe0e4de5390e0f47e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308531"
---
# <a name="state-property-ado"></a>State 属性 (ADO)


**适用于**：Access 2013、Office 2013

对所有适用的对象，指示其状态是打开还是关闭。

指示执行异步方法的所有适用对象，无论对象的当前状态是正在连接、执行还是检索。

## <a name="return-value"></a>返回值

返回一个 **Long** 值，该值可以为 [ObjectStateEnum](objectstateenum.md) 值之一。 默认值是 **adStateClosed**。

## <a name="remarks"></a>注解

可以随时使用 **State** 属性确定给定对象的当前状态。

对象的 **State** 属性可以是组合值。例如，如果正在执行某个语句，则此属性的值将为 **adStateOpen** 和 **adStateExecuting** 的组合值。

**State** 为只读属性。

