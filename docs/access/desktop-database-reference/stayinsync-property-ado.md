---
title: StayInSync 属性 (ADO)
TOCTitle: StayInSync Property (ADO)
ms:assetid: 02c95c10-4032-14e1-e506-f334a8787142
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248792(v=office.15)
ms:contentKeyID: 48542966
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f492b2c3f58084be55eca4787cde486dab29ca67
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467468"
---
# <a name="stayinsync-property-ado"></a><span data-ttu-id="5ab83-102">StayInSync 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="5ab83-102">StayInSync Property (ADO)</span></span>


<span data-ttu-id="5ab83-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5ab83-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5ab83-104">指示在分层[Recordset](recordset-object-ado.md)对象是否父行位置更改时，更改对基础子记录 （即*章节*） 的引用。</span><span class="sxs-lookup"><span data-stu-id="5ab83-104">Indicates, in a hierarchical [Recordset](recordset-object-ado.md) object, whether the reference to the underlying child records (that is, the *chapter*) changes when the parent row position changes.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="5ab83-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="5ab83-105">Settings and Return Values</span></span>

<span data-ttu-id="5ab83-106">设置或返回一个**布尔**值。</span><span class="sxs-lookup"><span data-stu-id="5ab83-106">Sets or returns a **Boolean** value.</span></span> <span data-ttu-id="5ab83-107">默认值为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="5ab83-107">The default value is **True**.</span></span> <span data-ttu-id="5ab83-108">如果 **，则返回 True**，章将更新的父**Recordset**对象更改的行位置; 如果如果**False**，章将继续即使父**Recordset**对象已更改行位置，请参阅上一章中的数据。</span><span class="sxs-lookup"><span data-stu-id="5ab83-108">If **True**, the chapter will be updated if the parent **Recordset** object changes row position; if **False**, the chapter will continue to refer to data in the previous chapter even though the parent **Recordset** object has changed row position.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ab83-109">备注</span><span class="sxs-lookup"><span data-stu-id="5ab83-109">Remarks</span></span>

<span data-ttu-id="5ab83-p102">此属性应用于分级 Recordset，例如由 [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 提供的记录集，而且必须先在父 **Recordset** 上设置才能检索子 **Recordset** 。此属性简化了分级记录集的导航操作。</span><span class="sxs-lookup"><span data-stu-id="5ab83-p102">This property applies to hierarchical Recordsets, such as those supported by the [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md), and must be set on the parent **Recordset** before the child **Recordset** is retrieved. This property simplifies navigating hierarchical recordsets.</span></span>

