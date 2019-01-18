---
title: MarshalOptions 属性 (ADO)
TOCTitle: MarshalOptions property (ADO)
ms:assetid: dc9c4e94-0725-210d-8251-079054541142
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250118(v=office.15)
ms:contentKeyID: 48548143
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 22a3662d3d14dd639069fa7aa48eda6f032fd2d1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704593"
---
# <a name="marshaloptions-property-ado"></a><span data-ttu-id="c524e-102">MarshalOptions 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c524e-102">MarshalOptions property (ADO)</span></span>


<span data-ttu-id="c524e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c524e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c524e-104">指示哪些记录要封送回服务器。</span><span class="sxs-lookup"><span data-stu-id="c524e-104">Indicates which records are to be marshaled back to the server.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="c524e-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="c524e-105">Settings And Return Values</span></span>

<span data-ttu-id="c524e-p101">设置或返回一个 [MarshalOptionsEnum](marshaloptionsenum.md) 值。默认值是 **adMarshalAll** 。</span><span class="sxs-lookup"><span data-stu-id="c524e-p101">Sets or returns a [MarshalOptionsEnum](marshaloptionsenum.md) value. The default value is **adMarshalAll**.</span></span>

## <a name="remarks"></a><span data-ttu-id="c524e-108">备注</span><span class="sxs-lookup"><span data-stu-id="c524e-108">Remarks</span></span>

<span data-ttu-id="c524e-109">在使用客户端[Recordset](recordset-object-ado.md)时，客户端已修改的记录写回中间层或通过称为封送，打包和跨线程发送接口方法参数的过程的技术的 web 服务器或进程边界。</span><span class="sxs-lookup"><span data-stu-id="c524e-109">When using a client-side [Recordset](recordset-object-ado.md), records that have been modified on the client are written back to the middle tier or web server through a technique called marshaling, the process of packaging and sending interface method parameters across thread or process boundaries.</span></span> <span data-ttu-id="c524e-110">已修改的远程数据封送回中间层或 web 服务器更新时，设置**MarshalOptions**属性可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="c524e-110">Setting the **MarshalOptions** property can improve performance when modified remote data is marshaled for updating back to the middle tier or web server.</span></span>

<span data-ttu-id="c524e-111">**远程数据服务用法**此属性只能在客户端**Recordset**上使用。</span><span class="sxs-lookup"><span data-stu-id="c524e-111">**Remote Data Service Usage**This property is used only on a client-side **Recordset**.</span></span>

