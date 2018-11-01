---
title: 参数化命令与干扰性 COMPUTE 命令
TOCTitle: Parameterized Commands with Intervening COMPUTE Commands
ms:assetid: ff3724cd-040b-4b5f-bb9b-e6a38fd938c9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250311(v=office.15)
ms:contentKeyID: 48548959
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c44afce969af77696e52cea3bc194d73eb2ddd25
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877252"
---
# <a name="parameterized-commands-with-intervening-compute-commands"></a>参数化命令与干扰性 COMPUTE 命令


**适用于**： Access 2013、 Office 2013

典型的参数化 Shape APPEND 命令包含一个用查询命令创建父 **Recordset** 的子句，以及一个用参数化查询命令（即包含参数占位符，即：问号"?"）的命令创建子 **Recordset** 的子句。生成的定形 **Recordset** 为两层，父记录集占据上层，子记录集占据下层。

现在，创建子 **Recordset** 的子句可以是任意数量的嵌套 Shape COMPUTE 命令，其中最深的嵌套命令包含参数化查询。生成的定形 **Recordset** 具有多层，父记录集占据最上层，子记录集占据最下层，由 Shape COMPUTE 命令生成的任意数量的 **Recordset** 占据中间层。

此功能通常用于调用 Shape COMPUTE 命令的聚合函数和分组功能，以创建包含子 **Recordset** 分析信息的中间 **Recordset** 对象。并且，由于此命令是参数化 Shape 命令，因而每次访问父记录集的章节列时，都可能检索新的子 **Recordset** 。由于中间层是由子记录集派生的，因此也会重新进行计算。

