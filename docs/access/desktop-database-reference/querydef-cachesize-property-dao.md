---
title: QueryDef.CacheSize 属性 (DAO)
TOCTitle: CacheSize Property
ms:assetid: a84d990e-8180-daa3-7640-47d2be8fd28b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821397(v=office.15)
ms:contentKeyID: 48546899
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0d826781bd668cff0a61c655e55834512a289c17
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28701707"
---
# <a name="querydefcachesize-property-dao"></a><span data-ttu-id="7f3ca-102">QueryDef.CacheSize 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="7f3ca-102">QueryDef.CacheSize property (DAO)</span></span>


<span data-ttu-id="7f3ca-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7f3ca-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7f3ca-p101">设置或返回从 ODBC 数据源中检索的、需要本地缓存的记录数。可读/写 **Long** 类型。</span><span class="sxs-lookup"><span data-stu-id="7f3ca-p101">Sets or returns the number of records retrieved from an ODBC data source that will be cached locally. Read/write **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f3ca-106">语法</span><span class="sxs-lookup"><span data-stu-id="7f3ca-106">Syntax</span></span>

<span data-ttu-id="7f3ca-107">*表达式*。CacheSize</span><span class="sxs-lookup"><span data-stu-id="7f3ca-107">*expression* .CacheSize</span></span>

<span data-ttu-id="7f3ca-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="7f3ca-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f3ca-109">注解</span><span class="sxs-lookup"><span data-stu-id="7f3ca-109">Remarks</span></span>

<span data-ttu-id="7f3ca-p102">**CacheSize** 属性值必须介于 5 和 1200 之间，但不得超过可用内存允许的大小。典型值为 100。设置为 0 时将关闭缓存。</span><span class="sxs-lookup"><span data-stu-id="7f3ca-p102">The value of the **CacheSize** property must be between 5 and 1200, but not greater than available memory will allow. A typical value is 100. A setting of 0 turns off caching.</span></span>

<span data-ttu-id="7f3ca-113">Microsoft Access 数据库引擎从缓存中请求位于缓存范围内的记录，同时从服务器中请求位于缓存范围以外的记录。</span><span class="sxs-lookup"><span data-stu-id="7f3ca-113">The Microsoft Access database engine requests records within the cache range from the cache, and it requests records outside the cache range from the server.</span></span>

<span data-ttu-id="7f3ca-114">从缓存中检索的记录并不能反映其他用户对源数据所做的并发更改。</span><span class="sxs-lookup"><span data-stu-id="7f3ca-114">Records retrieved from the cache don't reflect concurrent changes that other users made to the source data.</span></span>

