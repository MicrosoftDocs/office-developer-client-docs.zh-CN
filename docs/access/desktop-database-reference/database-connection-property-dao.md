---
title: Database.Connection Property (DAO)
TOCTitle: Connection Property
ms:assetid: 8b900ea4-9179-9ed1-bc0b-0576939bb2bd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197325(v=office.15)
ms:contentKeyID: 48546221
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d000d2f01bea7746fb249ab7f9acacc047029b21
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466620"
---
# <a name="databaseconnection-property-dao"></a><span data-ttu-id="8e0bf-102">Database.Connection Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="8e0bf-102">Database.Connection Property (DAO)</span></span>


<span data-ttu-id="8e0bf-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8e0bf-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="8e0bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e0bf-104">Syntax</span></span>

<span data-ttu-id="8e0bf-105">*表达式*。连接</span><span class="sxs-lookup"><span data-stu-id="8e0bf-105">*expression* .Connection</span></span>

<span data-ttu-id="8e0bf-106">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="8e0bf-106">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e0bf-107">注解</span><span class="sxs-lookup"><span data-stu-id="8e0bf-107">Remarks</span></span>

<span data-ttu-id="8e0bf-p101">使用 **Connection** 属性可获取指向对应于 **Database** 的 **Connection** 对象的引用。在 DAO 中， **Connection** 对象及其对应的 **Database** 对象只是指向相同对象的两个不同的对象变量引用。使用 [Connection](connection-database-property-dao.md) 对象的 \*\*\*\*Database\*\*\*\* 属性和 **Database** 对象的 **Connection** 属性可以更轻松地将通过 Microsoft Access 数据库引擎与 ODBC 数据源建立的连接更改为使用 ODBCDirect。</span><span class="sxs-lookup"><span data-stu-id="8e0bf-p101">Use the **Connection** property to obtain a reference to a **Connection** object that corresponds to the **Database**. In DAO, a **Connection** object and its corresponding **Database** object are simply two different object variable references to the same object. The **[Database](connection-database-property-dao.md)** property of a **Connection** object and the **Connection** property of a **Database** object make it easier to change connections to an ODBC data source through the Microsoft Access database engine to use ODBCDirect.</span></span>
