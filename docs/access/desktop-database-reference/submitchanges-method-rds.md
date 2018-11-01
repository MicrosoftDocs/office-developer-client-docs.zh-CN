---
title: SubmitChanges 方法 (RDS)
TOCTitle: SubmitChanges Method (RDS)
ms:assetid: ecaea12d-7e1a-095d-17e7-d631ef230b90
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250201(v=office.15)
ms:contentKeyID: 48548521
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 521728af91967d673a1c69f4e4812b0aaa73ce59
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25883881"
---
# <a name="submitchanges-method-rds"></a><span data-ttu-id="37ded-102">SubmitChanges 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="37ded-102">SubmitChanges Method (RDS)</span></span>


<span data-ttu-id="37ded-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="37ded-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="37ded-104">可向在 [Connect](recordset-object-ado.md) 属性或 [URL](connect-property-rds.md) 属性中指定的数据源提交在本地缓存且可更新的 [Recordset](url-property-rds.md) 的挂起更改。</span><span class="sxs-lookup"><span data-stu-id="37ded-104">Submits pending changes of the locally cached and updatable [Recordset](recordset-object-ado.md) to the data source specified in the [Connect](connect-property-rds.md) property or the [URL](url-property-rds.md) property.</span></span>

## <a name="syntax"></a><span data-ttu-id="37ded-105">语法</span><span class="sxs-lookup"><span data-stu-id="37ded-105">Syntax</span></span>

<span data-ttu-id="37ded-106">*DataControl*。SubmitChanges</span><span class="sxs-lookup"><span data-stu-id="37ded-106">*DataControl*.SubmitChanges</span></span>

<span data-ttu-id="37ded-107">*DataFactory*。SubmitChanges*连接* *Recordset*</span><span class="sxs-lookup"><span data-stu-id="37ded-107">*DataFactory*.SubmitChanges*Connection*, *Recordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="37ded-108">参数</span><span class="sxs-lookup"><span data-stu-id="37ded-108">Parameters</span></span>

  - <span data-ttu-id="37ded-109">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="37ded-109">*DataControl*</span></span>

  - <span data-ttu-id="37ded-110">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="37ded-110">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="37ded-111">*DataFactory*</span><span class="sxs-lookup"><span data-stu-id="37ded-111">*DataFactory*</span></span>

  - <span data-ttu-id="37ded-112">一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="37ded-112">An object variable that represents an [RDSServer.DataFactory](datafactory-object-rdsserver.md) object.</span></span>

  - <span data-ttu-id="37ded-113">*Connection*</span><span class="sxs-lookup"><span data-stu-id="37ded-113">*Connection*</span></span>

  - <span data-ttu-id="37ded-114">**字符串型** 值，表示用 **RDS.DataControl** 对象的 **Connect** 属性创建的连接。</span><span class="sxs-lookup"><span data-stu-id="37ded-114">A **String** value that represents the connection created with the **RDS.DataControl** object's **Connect** property.</span></span>

  - <span data-ttu-id="37ded-115">*Recordset*</span><span class="sxs-lookup"><span data-stu-id="37ded-115">*Recordset*</span></span>

  - <span data-ttu-id="37ded-116">一个代表 **Recordset** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="37ded-116">An object variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="37ded-117">备注</span><span class="sxs-lookup"><span data-stu-id="37ded-117">Remarks</span></span>

<span data-ttu-id="37ded-118">必须先设置 [Connect](connect-property-rds.md)、[Server](server-property-rds.md) 和 [SQL](https://msdn.microsoft.com/library/jj248989\(v=office.15\)) 属性，然后才能将 **SubmitChanges** 方法用于 **RDS.DataControl** 对象。</span><span class="sxs-lookup"><span data-stu-id="37ded-118">The [Connect](connect-property-rds.md), [Server](server-property-rds.md), and [SQL](https://msdn.microsoft.com/library/jj248989\(v=office.15\)) properties must be set before you can use the **SubmitChanges** method with the **RDS.DataControl** object.</span></span>

<span data-ttu-id="37ded-119">如果在调用 [SubmitChanges](cancelupdate-method-rds.md) 后，针对同一 **Recordset** 对象又调用 **CancelUpdate** 方法，则由于更改已提交， **CancelUpdate** 调用将失败。</span><span class="sxs-lookup"><span data-stu-id="37ded-119">If you call the [CancelUpdate](cancelupdate-method-rds.md) method after you have called **SubmitChanges** for the same **Recordset** object, the **CancelUpdate** call fails because the changes have already been committed.</span></span>

<span data-ttu-id="37ded-120">对于修改操作，只发送已更改的记录，并且所有更改要么都成功，要么都失败。</span><span class="sxs-lookup"><span data-stu-id="37ded-120">Only the changed records are sent for modification, and either all of the changes succeed or all of them fail together.</span></span>

<span data-ttu-id="37ded-121">**SubmitChanges**仅使用*默认* **RDSServer.DataFactory**对象。</span><span class="sxs-lookup"><span data-stu-id="37ded-121">You can use **SubmitChanges** only with the *default* **RDSServer.DataFactory** object.</span></span> <span data-ttu-id="37ded-122">自定义业务对象不能使用此方法。</span><span class="sxs-lookup"><span data-stu-id="37ded-122">Custom business objects can't use this method.</span></span>

<span data-ttu-id="37ded-123">如果设置了 **URL** 属性，则 **SubmitChanges** 将更改提交到 URL 指定的位置。</span><span class="sxs-lookup"><span data-stu-id="37ded-123">If the **URL** property has been set, **SubmitChanges** will submit changes to the location specified by the URL.</span></span>

