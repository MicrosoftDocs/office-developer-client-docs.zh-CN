---
title: Database. Connection 属性 (DAO)
TOCTitle: Connection Property
ms:assetid: 8b900ea4-9179-9ed1-bc0b-0576939bb2bd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197325(v=office.15)
ms:contentKeyID: 48546221
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 77d9bfa30dbfab21fd75de36b336a25e6af3187e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294993"
---
# <a name="databaseconnection-property-dao"></a><span data-ttu-id="c96f7-102">Database. Connection 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c96f7-102">Database.Connection property (DAO)</span></span>


<span data-ttu-id="c96f7-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c96f7-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="c96f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="c96f7-104">Syntax</span></span>

<span data-ttu-id="c96f7-105">*表达式*。联系</span><span class="sxs-lookup"><span data-stu-id="c96f7-105">*expression* .Connection</span></span>

<span data-ttu-id="c96f7-106">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c96f7-106">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c96f7-107">注解</span><span class="sxs-lookup"><span data-stu-id="c96f7-107">Remarks</span></span>

<span data-ttu-id="c96f7-108">使用 **Connection** 属性可获取指向对应于 **Database** 的 **Connection** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="c96f7-108">Use the **Connection** property to obtain a reference to a **Connection** object that corresponds to the **Database**.</span></span> <span data-ttu-id="c96f7-109">在 DAO 中，**Connection** 对象及其对应的 **Database** 对象只是指向相同对象的两个不同的对象变量引用。</span><span class="sxs-lookup"><span data-stu-id="c96f7-109">In DAO, a **Connection** object and its corresponding **Database** object are simply two different object variable references to the same object.</span></span> <span data-ttu-id="c96f7-110">**connection**对象的**[database](connection-database-property-dao.md)** 属性和**database**对象的**connection**属性使得通过 Microsoft Access 数据库引擎更改到 ODBC 数据源的连接变得更加容易, 以使用 ODBCDirect。</span><span class="sxs-lookup"><span data-stu-id="c96f7-110">The **[Database](connection-database-property-dao.md)** property of a **Connection** object and the **Connection** property of a **Database** object make it easier to change connections to an ODBC data source through the Microsoft Access database engine to use ODBCDirect.</span></span>

