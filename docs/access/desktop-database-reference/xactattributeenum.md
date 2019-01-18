---
title: XactAttributeEnum （访问桌面数据库参考 （英文）
TOCTitle: XactAttributeEnum
ms:assetid: 9206698b-7cfa-1229-2701-f2b6949e54fc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249643(v=office.15)
ms:contentKeyID: 48546366
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e79a6143c65637660b2d59b7c7efb6a21e8935bd
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718551"
---
# <a name="xactattributeenum"></a><span data-ttu-id="82eea-102">XactAttributeEnum</span><span class="sxs-lookup"><span data-stu-id="82eea-102">XactAttributeEnum</span></span>

<span data-ttu-id="82eea-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="82eea-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="82eea-104">指定 [Connection](connection-object-ado.md) 对象的事务属性。</span><span class="sxs-lookup"><span data-stu-id="82eea-104">Specifies the transaction attributes of a [Connection](connection-object-ado.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="82eea-105">常量</span><span class="sxs-lookup"><span data-stu-id="82eea-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="82eea-106">值</span><span class="sxs-lookup"><span data-stu-id="82eea-106">Value</span></span></p></th>
<th><p><span data-ttu-id="82eea-107">说明</span><span class="sxs-lookup"><span data-stu-id="82eea-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82eea-108"><strong>adXactAbortRetaining</strong></span><span class="sxs-lookup"><span data-stu-id="82eea-108"><strong>adXactAbortRetaining</strong></span></span></p></td>
<td><p><span data-ttu-id="82eea-109">262144</span><span class="sxs-lookup"><span data-stu-id="82eea-109">262144</span></span></p></td>
<td><p><span data-ttu-id="82eea-110">执行保留中止;即自动调用<a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">RollbackTrans</a>启动一个新的事务。</span><span class="sxs-lookup"><span data-stu-id="82eea-110">Performs retaining aborts; that is, calling <a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">RollbackTrans</a> automatically starts a new transaction.</span></span> <span data-ttu-id="82eea-111">并非所有提供程序支持此功能。</span><span class="sxs-lookup"><span data-stu-id="82eea-111">Not all providers support this.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82eea-112"><strong>adXactCommitRetaining</strong></span><span class="sxs-lookup"><span data-stu-id="82eea-112"><strong>adXactCommitRetaining</strong></span></span></p></td>
<td><p><span data-ttu-id="82eea-113">131072</span><span class="sxs-lookup"><span data-stu-id="82eea-113">131072</span></span></p></td>
<td><p><span data-ttu-id="82eea-114">执行保留提交;即自动调用<a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">CommitTrans</a>启动一个新的事务。</span><span class="sxs-lookup"><span data-stu-id="82eea-114">Performs retaining commits; that is, calling <a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">CommitTrans</a> automatically starts a new transaction.</span></span> <span data-ttu-id="82eea-115">并非所有提供程序支持此功能。</span><span class="sxs-lookup"><span data-stu-id="82eea-115">Not all providers support this.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="82eea-116">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="82eea-116">ADO/WFC equivalent</span></span>

<span data-ttu-id="82eea-117">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="82eea-117">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="82eea-118">常量</span><span class="sxs-lookup"><span data-stu-id="82eea-118">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82eea-119">AdoEnums.XactAttribute.ABORTRETAINING</span><span class="sxs-lookup"><span data-stu-id="82eea-119">AdoEnums.XactAttribute.ABORTRETAINING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82eea-120">AdoEnums.XactAttribute.COMMITRETAINING</span><span class="sxs-lookup"><span data-stu-id="82eea-120">AdoEnums.XactAttribute.COMMITRETAINING</span></span></p></td>
</tr>
</tbody>
</table>

