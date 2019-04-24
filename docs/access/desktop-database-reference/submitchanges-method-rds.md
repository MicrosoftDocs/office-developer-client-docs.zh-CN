---
title: SubmitChanges 方法 (RDS)
TOCTitle: SubmitChanges method (RDS)
ms:assetid: ecaea12d-7e1a-095d-17e7-d631ef230b90
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250201(v=office.15)
ms:contentKeyID: 48548521
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ea7f3e27a75b4483cb8cf46e27d4492f831cff33
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314397"
---
# <a name="submitchanges-method-rds"></a><span data-ttu-id="6deae-102">SubmitChanges 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="6deae-102">SubmitChanges method (RDS)</span></span>

<span data-ttu-id="6deae-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6deae-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6deae-104">可向在 [Connect](connect-property-rds.md) 属性或 [URL](url-property-rds.md) 属性中指定的数据源提交在本地缓存且可更新的 [Recordset](recordset-object-ado.md) 的挂起更改。</span><span class="sxs-lookup"><span data-stu-id="6deae-104">Submits pending changes of the locally cached and updatable [Recordset](recordset-object-ado.md) to the data source specified in the [Connect](connect-property-rds.md) property or the [URL](url-property-rds.md) property.</span></span>

## <a name="syntax"></a><span data-ttu-id="6deae-105">语法</span><span class="sxs-lookup"><span data-stu-id="6deae-105">Syntax</span></span>

<span data-ttu-id="6deae-106">*rds.datacontrol*。SubmitChanges</span><span class="sxs-lookup"><span data-stu-id="6deae-106">*DataControl*.SubmitChanges</span></span>

<span data-ttu-id="6deae-107">*DataFactory*。SubmitChanges*连接*、 *Recordset*</span><span class="sxs-lookup"><span data-stu-id="6deae-107">*DataFactory*.SubmitChanges*Connection*, *Recordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="6deae-108">参数</span><span class="sxs-lookup"><span data-stu-id="6deae-108">Parameters</span></span>

|<span data-ttu-id="6deae-109">参数</span><span class="sxs-lookup"><span data-stu-id="6deae-109">Parameter</span></span>|<span data-ttu-id="6deae-110">描述</span><span class="sxs-lookup"><span data-stu-id="6deae-110">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="6deae-111">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="6deae-111">*DataControl*</span></span> |<span data-ttu-id="6deae-112">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="6deae-112">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|
|<span data-ttu-id="6deae-113">*DataFactory*</span><span class="sxs-lookup"><span data-stu-id="6deae-113">*DataFactory*</span></span> |<span data-ttu-id="6deae-114">一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="6deae-114">An object variable that represents an [RDSServer.DataFactory](datafactory-object-rdsserver.md) object.</span></span>|
|<span data-ttu-id="6deae-115">*Connection*</span><span class="sxs-lookup"><span data-stu-id="6deae-115">*Connection*</span></span> |<span data-ttu-id="6deae-116">**字符串型** 值，表示用 **RDS.DataControl** 对象的 **Connect** 属性创建的连接。</span><span class="sxs-lookup"><span data-stu-id="6deae-116">A **String** value that represents the connection created with the **RDS.DataControl** object's **Connect** property.</span></span>|
|<span data-ttu-id="6deae-117">*Recordset*</span><span class="sxs-lookup"><span data-stu-id="6deae-117">*Recordset*</span></span> |<span data-ttu-id="6deae-118">一个代表 **Recordset** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="6deae-118">An object variable that represents a **Recordset** object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6deae-119">注解</span><span class="sxs-lookup"><span data-stu-id="6deae-119">Remarks</span></span>

<span data-ttu-id="6deae-120">必须先设置 [Connect](connect-property-rds.md)、[Server](server-property-rds.md) 和 [SQL](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado) 属性，然后才能将 **SubmitChanges** 方法用于 **RDS.DataControl** 对象。</span><span class="sxs-lookup"><span data-stu-id="6deae-120">The [Connect](connect-property-rds.md), [Server](server-property-rds.md), and [SQL](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado) properties must be set before you can use the **SubmitChanges** method with the **RDS.DataControl** object.</span></span>

<span data-ttu-id="6deae-121">如果在调用 **SubmitChanges** 后，针对同一 **Recordset** 对象又调用 [CancelUpdate](cancelupdate-method-rds.md) 方法，则由于更改已提交，**CancelUpdate** 调用将失败。</span><span class="sxs-lookup"><span data-stu-id="6deae-121">If you call the [CancelUpdate](cancelupdate-method-rds.md) method after you have called **SubmitChanges** for the same **Recordset** object, the **CancelUpdate** call fails because the changes have already been committed.</span></span>

<span data-ttu-id="6deae-122">对于修改操作，只发送已更改的记录，并且所有更改要么都成功，要么都失败。</span><span class="sxs-lookup"><span data-stu-id="6deae-122">Only the changed records are sent for modification, and either all of the changes succeed or all of them fail together.</span></span>

<span data-ttu-id="6deae-123">只能将**SubmitChanges**用于*默认*的**rdsserver.datafactory DataFactory**对象。</span><span class="sxs-lookup"><span data-stu-id="6deae-123">You can use **SubmitChanges** only with the *default* **RDSServer.DataFactory** object.</span></span> <span data-ttu-id="6deae-124">自定义业务对象不能使用此方法。</span><span class="sxs-lookup"><span data-stu-id="6deae-124">Custom business objects can't use this method.</span></span>

<span data-ttu-id="6deae-125">如果设置了 **URL** 属性，则 **SubmitChanges** 将更改提交到 URL 指定的位置。</span><span class="sxs-lookup"><span data-stu-id="6deae-125">If the **URL** property has been set, **SubmitChanges** will submit changes to the location specified by the URL.</span></span>

