---
title: WITH OWNERACCESS OPTION 声明 (Microsoft Access SQL)
TOCTitle: WITH OWNERACCESS OPTION Declaration (Microsoft Access SQL)
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
ms.openlocfilehash: b47b9fcc5b3c4422ec60bbdaf06193533c20b6e9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468400"
---
# <a name="with-owneraccess-option-declaration-microsoft-access-sql"></a><span data-ttu-id="b9580-102">WITH OWNERACCESS OPTION 声明 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="b9580-102">WITH OWNERACCESS OPTION Declaration (Microsoft Access SQL)</span></span>


<span data-ttu-id="b9580-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b9580-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b9580-104">在使用安全工作组的多用户环境中，通过对查询使用这个声明，可以向执行该查询的用户授予与查询所有者同等的权限。</span><span class="sxs-lookup"><span data-stu-id="b9580-104">In a multiuser environment with a secure workgroup, use this declaration with a query to give the user who runs the query the same permissions as the query's owner.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9580-105">语法</span><span class="sxs-lookup"><span data-stu-id="b9580-105">Syntax</span></span>

<span data-ttu-id="b9580-106">*sqlstatement*与 OWNERACCESS OPTION</span><span class="sxs-lookup"><span data-stu-id="b9580-106">*sqlstatement* WITH OWNERACCESS OPTION</span></span>

## <a name="remarks"></a><span data-ttu-id="b9580-107">说明</span><span class="sxs-lookup"><span data-stu-id="b9580-107">Remarks</span></span>

<span data-ttu-id="b9580-108">WITH OWNERACCESS OPTION 声明是可选的。</span><span class="sxs-lookup"><span data-stu-id="b9580-108">The WITH OWNERACCESS OPTION declaration is optional.</span></span>

<span data-ttu-id="b9580-109">下面的示例使用户能够查看到薪金信息（即使该用户并不拥有查看 Payroll 表的权限，并假设查询的拥有者有此权限）。</span><span class="sxs-lookup"><span data-stu-id="b9580-109">The following example enables the user to view salary information (even if the user does not otherwise have permission to view the Payroll table), provided that the query's owner does have that permission:</span></span>

``` sql
SELECT LastName, 
FirstName, Salary
FROM Employees 
ORDER BY LastName 
WITH OWNERACCESS OPTION;
```

<span data-ttu-id="b9580-110">如果要禁止用户创建表或在表中添加记录，可以使用 WITH OWNERACCESS OPTION 来让用户能够运行生成表 追加查询。</span><span class="sxs-lookup"><span data-stu-id="b9580-110">If a user is otherwise prevented from creating or adding to a table, you can use WITH OWNERACCESS OPTION to enable the user to run a make-table or append query.</span></span>

<span data-ttu-id="b9580-111">如果希望应用工作组安全设置和用户的权限，请不要包含 WITH OWNERACCESS OPTION 声明。</span><span class="sxs-lookup"><span data-stu-id="b9580-111">If you want to enforce workgroup security settings and users' permissions, do not include the WITH OWNERACCESS OPTION declaration.</span></span>

<span data-ttu-id="b9580-p101">这个选项需要您有权访问与数据库关联的 System.mdw 文件。它仅在安全的多用户实现中才是有用的。</span><span class="sxs-lookup"><span data-stu-id="b9580-p101">This option requires you to have access to the System.mdw file associated with the database. It is useful only in secured multiuser implementations.</span></span>

