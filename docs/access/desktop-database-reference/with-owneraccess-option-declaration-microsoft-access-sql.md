---
title: 与 OWNERACCESS OPTION 声明 (Microsoft Access SQL)
TOCTitle: WITH OWNERACCESS OPTION declaration (Microsoft Access SQL)
ms:assetid: 82e51071-12b2-e97e-07b4-27ffceda831e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196724(v=office.15)
ms:contentKeyID: 48545993
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277584
dev_langs:
- sql
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 0eca4738d07c54b049073aaf5d4b802864761fa5
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25920597"
---
# <a name="with-owneraccess-option-declaration-microsoft-access-sql"></a>与 OWNERACCESS OPTION 声明 (Microsoft Access SQL)


**适用于**： Access 2013、 Office 2013

在使用安全工作组的多用户环境中，通过对查询使用这个声明，可以向执行该查询的用户授予与查询所有者同等的权限。

## <a name="syntax"></a>语法

*sqlstatement*与 OWNERACCESS OPTION

## <a name="remarks"></a>说明

WITH OWNERACCESS OPTION 声明是可选的。

下面的示例使用户能够查看到薪金信息（即使该用户并不拥有查看 Payroll 表的权限，并假设查询的拥有者有此权限）。

``` sql
SELECT LastName, 
FirstName, Salary
FROM Employees 
ORDER BY LastName 
WITH OWNERACCESS OPTION;
```

如果要禁止用户创建表或在表中添加记录，可以使用 WITH OWNERACCESS OPTION 来让用户能够运行生成表 追加查询。

如果希望应用工作组安全设置和用户的权限，请不要包含 WITH OWNERACCESS OPTION 声明。

这个选项需要您有权访问与数据库关联的 System.mdw 文件。它仅在安全的多用户实现中才是有用的。

