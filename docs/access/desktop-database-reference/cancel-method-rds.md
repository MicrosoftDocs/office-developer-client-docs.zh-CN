---
title: Cancel 方法 (RDS)
TOCTitle: Cancel method (RDS)
ms:assetid: 08f667c2-7a3f-c2e7-7bdf-3eb533defa33
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248827(v=office.15)
ms:contentKeyID: 48543109
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 35322ec058d31f92288fd06a4e8434a4256c2d74
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296645"
---
# <a name="cancel-method-rds"></a>Cancel 方法 (RDS)


**适用于**：Access 2013、Office 2013

取消执行挂起的异步方法调用。

## <a name="syntax"></a>语法

*RDS*。 *rds.datacontrol*。取消

## <a name="remarks"></a>注解

当调用 **Cancel** 时，[ReadyState](readystate-property-rds.md) 会自动设置为 **adcReadyStateLoaded**，并且 [Recordset](recordset-object-ado.md) 将为空。

