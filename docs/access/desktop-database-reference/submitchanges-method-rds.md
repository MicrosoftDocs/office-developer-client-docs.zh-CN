---
title: SubmitChanges 方法 (RDS)
TOCTitle: SubmitChanges method (RDS)
ms:assetid: ecaea12d-7e1a-095d-17e7-d631ef230b90
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250201(v=office.15)
ms:contentKeyID: 48548521
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4b5c18aa12519e9206702eb2a152e6f0d084edc9
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026342"
---
# <a name="submitchanges-method-rds"></a><span data-ttu-id="c71fb-102">SubmitChanges 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="c71fb-102">SubmitChanges method (RDS)</span></span>

<span data-ttu-id="c71fb-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c71fb-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c71fb-104">可向在 [Connect](recordset-object-ado.md) 属性或 [URL](connect-property-rds.md) 属性中指定的数据源提交在本地缓存且可更新的 [Recordset](url-property-rds.md) 的挂起更改。</span><span class="sxs-lookup"><span data-stu-id="c71fb-104">Submits pending changes of the locally cached and updatable [Recordset](recordset-object-ado.md) to the data source specified in the [Connect](connect-property-rds.md) property or the [URL](url-property-rds.md) property.</span></span>

## <a name="syntax"></a><span data-ttu-id="c71fb-105">语法</span><span class="sxs-lookup"><span data-stu-id="c71fb-105">Syntax</span></span>

<span data-ttu-id="c71fb-106">*DataControl*。SubmitChanges</span><span class="sxs-lookup"><span data-stu-id="c71fb-106">*DataControl*.SubmitChanges</span></span>

<span data-ttu-id="c71fb-107">*DataFactory*。SubmitChanges*连接* *Recordset*</span><span class="sxs-lookup"><span data-stu-id="c71fb-107">*DataFactory*.SubmitChanges*Connection*, *Recordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="c71fb-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="c71fb-108">Parameters</span></span>

|<span data-ttu-id="c71fb-109">参数</span><span class="sxs-lookup"><span data-stu-id="c71fb-109">Parameter</span></span>|<span data-ttu-id="c71fb-110">说明</span><span class="sxs-lookup"><span data-stu-id="c71fb-110">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="c71fb-111">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="c71fb-111">*DataControl*</span></span> |<span data-ttu-id="c71fb-112">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="c71fb-112">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|
|<span data-ttu-id="c71fb-113">*DataFactory*</span><span class="sxs-lookup"><span data-stu-id="c71fb-113">*DataFactory*</span></span> |<span data-ttu-id="c71fb-114">一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="c71fb-114">An object variable that represents an [RDSServer.DataFactory](datafactory-object-rdsserver.md) object.</span></span>|
|<span data-ttu-id="c71fb-115">*Connection*</span><span class="sxs-lookup"><span data-stu-id="c71fb-115">*Connection*</span></span> |<span data-ttu-id="c71fb-116">**字符串型** 值，表示用 **RDS.DataControl** 对象的 **Connect** 属性创建的连接。</span><span class="sxs-lookup"><span data-stu-id="c71fb-116">A **String** value that represents the connection created with the **RDS.DataControl** object's **Connect** property.</span></span>|
|<span data-ttu-id="c71fb-117">*Recordset*</span><span class="sxs-lookup"><span data-stu-id="c71fb-117">*Recordset*</span></span> |<span data-ttu-id="c71fb-118">一个代表 **Recordset** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="c71fb-118">An object variable that represents a **Recordset** object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c71fb-119">备注</span><span class="sxs-lookup"><span data-stu-id="c71fb-119">Remarks</span></span>

<span data-ttu-id="c71fb-120">必须先设置 [Connect](connect-property-rds.md)、[Server](server-property-rds.md) 和 [SQL](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado) 属性，然后才能将 **SubmitChanges** 方法用于 **RDS.DataControl** 对象。</span><span class="sxs-lookup"><span data-stu-id="c71fb-120">The [Connect](connect-property-rds.md), [Server](server-property-rds.md), and [SQL](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado) properties must be set before you can use the **SubmitChanges** method with the **RDS.DataControl** object.</span></span>

<span data-ttu-id="c71fb-121">如果在调用 [SubmitChanges](cancelupdate-method-rds.md) 后，针对同一 **Recordset** 对象又调用 **CancelUpdate** 方法，则由于更改已提交， **CancelUpdate** 调用将失败。</span><span class="sxs-lookup"><span data-stu-id="c71fb-121">If you call the [CancelUpdate](cancelupdate-method-rds.md) method after you have called **SubmitChanges** for the same **Recordset** object, the **CancelUpdate** call fails because the changes have already been committed.</span></span>

<span data-ttu-id="c71fb-122">对于修改操作，只发送已更改的记录，并且所有更改要么都成功，要么都失败。</span><span class="sxs-lookup"><span data-stu-id="c71fb-122">Only the changed records are sent for modification, and either all of the changes succeed or all of them fail together.</span></span>

<span data-ttu-id="c71fb-123">**SubmitChanges**仅使用*默认* **RDSServer.DataFactory**对象。</span><span class="sxs-lookup"><span data-stu-id="c71fb-123">You can use **SubmitChanges** only with the *default* **RDSServer.DataFactory** object.</span></span> <span data-ttu-id="c71fb-124">自定义业务对象不能使用此方法。</span><span class="sxs-lookup"><span data-stu-id="c71fb-124">Custom business objects can't use this method.</span></span>

<span data-ttu-id="c71fb-125">如果设置了 **URL** 属性，则 **SubmitChanges** 将更改提交到 URL 指定的位置。</span><span class="sxs-lookup"><span data-stu-id="c71fb-125">If the **URL** property has been set, **SubmitChanges** will submit changes to the location specified by the URL.</span></span>

