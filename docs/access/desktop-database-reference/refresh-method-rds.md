---
title: Refresh 方法 (RDS)
TOCTitle: Refresh method (RDS)
ms:assetid: 968baa7c-9128-7155-a1eb-d77aedda6601
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249668(v=office.15)
ms:contentKeyID: 48546450
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 60de3b25e5eedc277eaafbe4bd1c078863e13f7b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718719"
---
# <a name="refresh-method-rds"></a><span data-ttu-id="1174b-102">Refresh 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="1174b-102">Refresh method (RDS)</span></span>

<span data-ttu-id="1174b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1174b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1174b-104">可重新查询在 [Connect](connect-property-rds.md) 属性中指定的数据源并更新查询结果。</span><span class="sxs-lookup"><span data-stu-id="1174b-104">Requeries the data source specified in the [Connect](connect-property-rds.md) property and updates the query results.</span></span>

## <a name="syntax"></a><span data-ttu-id="1174b-105">语法</span><span class="sxs-lookup"><span data-stu-id="1174b-105">Syntax</span></span>

<span data-ttu-id="1174b-106">*DataControl*。刷新</span><span class="sxs-lookup"><span data-stu-id="1174b-106">*DataControl*.Refresh</span></span>

## <a name="parameters"></a><span data-ttu-id="1174b-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="1174b-107">Parameters</span></span>

|<span data-ttu-id="1174b-108">参数</span><span class="sxs-lookup"><span data-stu-id="1174b-108">Parameter</span></span>|<span data-ttu-id="1174b-109">说明</span><span class="sxs-lookup"><span data-stu-id="1174b-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="1174b-110">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="1174b-110">*DataControl*</span></span> |<span data-ttu-id="1174b-111">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="1174b-111">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1174b-112">备注</span><span class="sxs-lookup"><span data-stu-id="1174b-112">Remarks</span></span>

<span data-ttu-id="1174b-p101">在使用 [Refresh](connect-property-rds.md) 方法之前，必须设置 [Connect](server-property-rds.md)、[Server](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado) 和 **SQL** 属性。窗体上与 **RDS.DataControl** 对象关联的所有数据绑定控件都将反映新的记录集，之前存在的任何 [Recordset](recordset-object-ado.md) 对象都被释放，任何未保存的更改都被放弃。 **Refresh** 方法自动使第一条记录成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="1174b-p101">You must set the [Connect](connect-property-rds.md), [Server](server-property-rds.md), and [SQL](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado) properties before you use the **Refresh** method. All data-bound controls on the form associated with an **RDS.DataControl** object will reflect the new set of records. Any pre-existing [Recordset](recordset-object-ado.md) object is released, and any unsaved changes are discarded. The **Refresh** method automatically makes the first record the current record.</span></span>

<span data-ttu-id="1174b-p102">在处理数据时，最好定期调用 **Refresh** 方法。如果检索数据后将其在客户端计算机上放置一段时间，该数据很可能会过期，而您所做的任何更改都有可能失败，因为其他人可能在您之前更改了记录并提交了更改。</span><span class="sxs-lookup"><span data-stu-id="1174b-p102">It's a good idea to call the **Refresh** method periodically when you work with data. If you retrieve data, and then leave it on your client machine for a while, it is likely to become out of date. It's possible that any changes you make will fail, because someone else might have changed the record and submitted changes before you.</span></span>

