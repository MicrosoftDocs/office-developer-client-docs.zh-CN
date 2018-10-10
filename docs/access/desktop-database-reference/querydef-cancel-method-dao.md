---
title: QueryDef.Cancel Method (DAO)
TOCTitle: Cancel Method
ms:assetid: 91e61012-c01c-4c24-185c-bdadb7f33a58
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197642(v=office.15)
ms:contentKeyID: 48546364
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1055470
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 17e6c98851aa20a6a094223eeabb68fe40e719d5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466289"
---
# <a name="querydefcancel-method-dao"></a><span data-ttu-id="31cad-102">QueryDef.Cancel Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="31cad-102">QueryDef.Cancel Method (DAO)</span></span>


<span data-ttu-id="31cad-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="31cad-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="31cad-104">语法</span><span class="sxs-lookup"><span data-stu-id="31cad-104">Syntax</span></span>

<span data-ttu-id="31cad-105">*表达式*。取消</span><span class="sxs-lookup"><span data-stu-id="31cad-105">*expression* .Cancel</span></span>

<span data-ttu-id="31cad-106">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="31cad-106">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="31cad-107">说明</span><span class="sxs-lookup"><span data-stu-id="31cad-107">Remarks</span></span>

<span data-ttu-id="31cad-108">使用**Cancel**方法可以终止执行异步**Execute**或**OpenConnection**方法调用 （即，该方法使用 dbRunAsync 选项调用）。</span><span class="sxs-lookup"><span data-stu-id="31cad-108">Use the **Cancel** method to terminate execution of an asynchronous **Execute** or **OpenConnection** method call (that is, the method was invoked with the dbRunAsync option).</span></span> <span data-ttu-id="31cad-109">如果您正在尝试进行终止的方法中未使用 dbRunAsync，则**取消**将返回一个运行时错误。</span><span class="sxs-lookup"><span data-stu-id="31cad-109">**Cancel** will return a run-time error if dbRunAsync was not used in the method you're trying to terminate.</span></span>

