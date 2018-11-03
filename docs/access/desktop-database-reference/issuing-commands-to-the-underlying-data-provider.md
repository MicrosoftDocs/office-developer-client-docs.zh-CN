---
title: 向基础数据提供程序发出命令
TOCTitle: Issuing commands to the underlying data provider
ms:assetid: 9d8ef3f3-d93c-af67-3114-d2c36c78a802
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249716(v=office.15)
ms:contentKeyID: 48546626
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 142772aaff5080a6e2522ab31884f2ff2319c8a7
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944632"
---
# <a name="issuing-commands-to-the-underlying-data-provider"></a>向基础数据提供程序发出命令

**适用于**： Access 2013、 Office 2013

任何不以 SHAPE 开头的命令都将传递到数据提供程序。 这等价于以"SHAPE {provider command}"的形式发出 Shape 命令。 这些命令执行*不*需要生成**Recordset**。 例如，假如数据提供程序支持 DROP TABLE，则"SHAPE {DROP TABLE MyTable}"是完全有效的 Shape 命令。

此功能允许正常提供程序命令和 Shape 命令共享相同的连接和事务。

