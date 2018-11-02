---
title: Recordset2.Cancel 方法 (DAO)
TOCTitle: Cancel Method
ms:assetid: cae49f36-3aad-80d8-c15f-a7a584aa2e9b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834366(v=office.15)
ms:contentKeyID: 48547703
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 159f476b592a8c944df2dc4570d84377c89b5043
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929228"
---
# <a name="recordset2cancel-method-dao"></a><span data-ttu-id="280dd-102">Recordset2.Cancel 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="280dd-102">Recordset2.Cancel method (DAO)</span></span>


<span data-ttu-id="280dd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="280dd-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="280dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="280dd-104">Syntax</span></span>

<span data-ttu-id="280dd-105">*表达式*。取消</span><span class="sxs-lookup"><span data-stu-id="280dd-105">*expression* .Cancel</span></span>

<span data-ttu-id="280dd-106">*表达式*一个返回**Recordset2**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="280dd-106">*expression* An expression that returns a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="280dd-107">说明</span><span class="sxs-lookup"><span data-stu-id="280dd-107">Remarks</span></span>

<span data-ttu-id="280dd-108">使用**Cancel**方法可以终止执行异步**Execute**或**OpenConnection**方法调用 （即，该方法使用 dbRunAsync 选项调用）。</span><span class="sxs-lookup"><span data-stu-id="280dd-108">Use the **Cancel** method to terminate execution of an asynchronous **Execute** or **OpenConnection** method call (that is, the method was invoked with the dbRunAsync option).</span></span> <span data-ttu-id="280dd-109">如果您正在尝试进行终止的方法中未使用 dbRunAsync，则**取消**将返回一个运行时错误。</span><span class="sxs-lookup"><span data-stu-id="280dd-109">**Cancel** will return a run-time error if dbRunAsync was not used in the method you're trying to terminate.</span></span>

