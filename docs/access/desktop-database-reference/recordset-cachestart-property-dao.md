---
title: CacheStart 属性 (DAO)
TOCTitle: CacheStart Property
ms:assetid: 03814312-660a-d8e9-8a7b-bc14d66e05ab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844802(v=office.15)
ms:contentKeyID: 48542986
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053171
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 514f109f0eed902287e519bcd7a729397e70eaa5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300614"
---
# <a name="recordsetcachestart-property-dao"></a><span data-ttu-id="27bbd-102">CacheStart 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="27bbd-102">Recordset.CacheStart property (DAO)</span></span>


<span data-ttu-id="27bbd-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="27bbd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="27bbd-104">设置或返回一个值，该值指定动态集类型 Recordset 对象（包含从 ODBC 数据源本地缓存的数据）中的第一条记录的书签（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="27bbd-104">Sets or returns a value that specifies the bookmark of the first record in a dynaset-type Recordset object containing data to be locally cached from an ODBC data source (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="27bbd-105">语法</span><span class="sxs-lookup"><span data-stu-id="27bbd-105">Syntax</span></span>

<span data-ttu-id="27bbd-106">*表达式*。CacheStart</span><span class="sxs-lookup"><span data-stu-id="27bbd-106">*expression* .CacheStart</span></span>

<span data-ttu-id="27bbd-107">*表达式*一个代表**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="27bbd-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="27bbd-108">注解</span><span class="sxs-lookup"><span data-stu-id="27bbd-108">Remarks</span></span>

<span data-ttu-id="27bbd-p101">如果使用 **Recordset** 对象从远程服务器检索数据，数据缓存可以提高性能。缓存是内存中的一个位置，用于保存最近从服务器检索的数据；如果用户在应用程序正在运行时再次请求数据，缓存将发挥作用。用户请求数据时，Microsoft Access 数据库引擎将首先检查所请求数据的缓存，而不是从服务器检索此数据（从服务器检索会花费较长时间）。缓存只保存来自 ODBC 数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="27bbd-p101">Data caching improves performance if you use **Recordset** objects to retrieve data from a remote server. A cache is a space in local memory that holds the data most recently retrieved from the server; this is useful if users request the data again while the application is running. When users request data, the Microsoft Access database engine checks the cache for the requested data first rather than retrieving it from the server, which takes more time. The cache only saves data that comes from an ODBC data source.</span></span>

<span data-ttu-id="27bbd-p102">任何 Microsoft Access 数据库引擎连接的 ODBC 数据源（例如链接表）都可以有一个本地缓存。若要创建缓存，请从远程数据源打开 **Recordset** 对象，设置 **CacheSize** 和 **[CacheStart](recordset-cachestart-property-dao.md)** 属性，然后使用 **[FillCache](recordset-fillcache-method-dao.md)** 方法，或者使用 **Move** 方法遍历记录。</span><span class="sxs-lookup"><span data-stu-id="27bbd-p102">Any Microsoft Access database engine-connected ODBC data source, such as a linked table, can have a local cache. To create the cache, open a **Recordset** object from the remote data source, set the **CacheSize** and **[CacheStart](recordset-cachestart-property-dao.md)** properties, and then use the **[FillCache](recordset-fillcache-method-dao.md)** method, or step through the records by using the **Move** methods.</span></span>

<span data-ttu-id="27bbd-p103">**CacheStart** 属性设置是要缓存的 **Recordset** 对象中的第一条记录的书签。可以使用任何记录的书签来设置 **CacheStart** 属性。将您要启动缓存的记录作为当前记录，并将 **CacheStart** 属性设置为等同于 **[Bookmark](recordset-bookmark-property-dao.md)** 属性。</span><span class="sxs-lookup"><span data-stu-id="27bbd-p103">The **CacheStart** property setting is the bookmark of the first record in the **Recordset** object to be cached. You can use the bookmark of any record to set the **CacheStart** property. Make the record you want to start the cache the current record, and set the **CacheStart** property equal to the **[Bookmark](recordset-bookmark-property-dao.md)** property.</span></span>

<span data-ttu-id="27bbd-118">Microsoft Access 数据库引擎从缓存中请求位于缓存范围内的记录，同时从服务器中请求位于缓存范围以外的记录。</span><span class="sxs-lookup"><span data-stu-id="27bbd-118">The Microsoft Access database engine requests records within the cache range from the cache, and it requests records outside the cache range from the server.</span></span>

<span data-ttu-id="27bbd-119">从缓存中检索的记录并不能反映其他用户对源数据所做的并发更改。</span><span class="sxs-lookup"><span data-stu-id="27bbd-119">Records retrieved from the cache don't reflect changes made concurrently to the source data by other users.</span></span>

<span data-ttu-id="27bbd-120">若要强制更新所有缓存的数据，请将 **Recordset** 对象的 **CacheSize** 属性设置为 0，再将它重置为最初请求的缓存的大小，然后使用 **FillCache** 方法。</span><span class="sxs-lookup"><span data-stu-id="27bbd-120">To force an update of all the cached data, set the **CacheSize** property of the **Recordset** object to 0, re-set it to the size of the cache you originally requested, and then use the **FillCache** method.</span></span>

