---
title: Cancel 方法 (ADO)
TOCTitle: Cancel Method (ADO)
ms:assetid: 747edc04-a5cc-3631-2d0b-82e7e41a76b7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249476(v=office.15)
ms:contentKeyID: 48545662
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231032
f1_categories:
- Office.Version=v15
ms.openlocfilehash: a257c5a8b3a4d597c8ddee7d882512b6a5fcdc08
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467673"
---
# <a name="cancel-method-ado"></a><span data-ttu-id="64aba-102">Cancel 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="64aba-102">Cancel Method (ADO)</span></span>


<span data-ttu-id="64aba-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="64aba-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="64aba-104">用于取消执行挂起的异步方法调用。</span><span class="sxs-lookup"><span data-stu-id="64aba-104">Cancels execution of a pending, asynchronous method call.</span></span>

## <a name="syntax"></a><span data-ttu-id="64aba-105">语法</span><span class="sxs-lookup"><span data-stu-id="64aba-105">Syntax</span></span>

<span data-ttu-id="64aba-106">*对象*。取消</span><span class="sxs-lookup"><span data-stu-id="64aba-106">*object*.Cancel</span></span>

## <a name="remarks"></a><span data-ttu-id="64aba-107">说明</span><span class="sxs-lookup"><span data-stu-id="64aba-107">Remarks</span></span>

<span data-ttu-id="64aba-108">**Cancel** 方法用于终止异步方法调用（即用 **adAsyncConnect** 、 **adAsyncExecute** 或 **adAsyncFetch** 选项调用的方法）的执行。</span><span class="sxs-lookup"><span data-stu-id="64aba-108">Use the **Cancel** method to terminate execution of an asynchronous method call (that is, a method invoked with the **adAsyncConnect**, **adAsyncExecute**, or **adAsyncFetch** option).</span></span>

<span data-ttu-id="64aba-109">下表显示了对特定对象类型使用 **Cancel** 方法时终止的任务。</span><span class="sxs-lookup"><span data-stu-id="64aba-109">The following table shows what task is terminated when you use the **Cancel** method on a particular type of object.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><br />
<span data-ttu-id="64aba-110">如果 <em>object</em> 为</span><span class="sxs-lookup"><span data-stu-id="64aba-110">If <em>object</em> is a</span></span></p></th>
<th><p><span data-ttu-id="64aba-111">则终止对此方法的最后一次异步调用</span><span class="sxs-lookup"><span data-stu-id="64aba-111">The last asynchronous call to this method is terminated</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64aba-112"><a href="command-object-ado.md">Command</a></span><span class="sxs-lookup"><span data-stu-id="64aba-112"><a href="command-object-ado.md">Command</a></span></span></p></td>
<td><p><span data-ttu-id="64aba-113"><a href="https://msdn.microsoft.com/library/jj248785(v=office.15)">Execute</a></span><span class="sxs-lookup"><span data-stu-id="64aba-113"><a href="https://msdn.microsoft.com/library/jj248785(v=office.15)">Execute</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64aba-114"><a href="connection-object-ado.md">Connection</a></span><span class="sxs-lookup"><span data-stu-id="64aba-114"><a href="connection-object-ado.md">Connection</a></span></span></p></td>
<td><p><span data-ttu-id="64aba-115"><a href="https://msdn.microsoft.com/library/jj249832(v=office.15)">Execute</a> 或 <a href="open-method-ado-connection.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="64aba-115"><a href="https://msdn.microsoft.com/library/jj249832(v=office.15)">Execute</a> or <a href="open-method-ado-connection.md">Open</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64aba-116"><a href="record-object-ado.md">Record</a></span><span class="sxs-lookup"><span data-stu-id="64aba-116"><a href="record-object-ado.md">Record</a></span></span></p></td>
<td><p><span data-ttu-id="64aba-117"><a href="copyrecord-method-ado.md">CopyRecord</a>、<a href="deleterecord-method-ado.md">DeleteRecord</a>、<a href="moverecord-method-ado.md">MoveRecord</a> 或 <a href="open-method-ado-record.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="64aba-117"><a href="copyrecord-method-ado.md">CopyRecord</a>, <a href="deleterecord-method-ado.md">DeleteRecord</a>, <a href="moverecord-method-ado.md">MoveRecord</a>, or <a href="open-method-ado-record.md">Open</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64aba-118"><a href="recordset-object-ado.md">Recordset</a></span><span class="sxs-lookup"><span data-stu-id="64aba-118"><a href="recordset-object-ado.md">Recordset</a></span></span></p></td>
<td><p><span data-ttu-id="64aba-119"><a href="open-method-ado-recordset.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="64aba-119"><a href="open-method-ado-recordset.md">Open</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64aba-120"><a href="stream-object-ado.md">Stream</a></span><span class="sxs-lookup"><span data-stu-id="64aba-120"><a href="stream-object-ado.md">Stream</a></span></span></p></td>
<td><p><span data-ttu-id="64aba-121"><a href="open-method-ado-stream.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="64aba-121"><a href="open-method-ado-stream.md">Open</a></span></span></p></td>
</tr>
</tbody>
</table>
