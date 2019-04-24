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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289768"
---
# <a name="marshaloptions-property-ado"></a><span data-ttu-id="6a93d-102">MarshalOptions 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="6a93d-102">MarshalOptions property (ADO)</span></span>


<span data-ttu-id="6a93d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6a93d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6a93d-104">指示哪些记录要封送回服务器。</span><span class="sxs-lookup"><span data-stu-id="6a93d-104">Indicates which records are to be marshaled back to the server.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="6a93d-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="6a93d-105">Settings And Return Values</span></span>

<span data-ttu-id="6a93d-p101">设置或返回一个 [MarshalOptionsEnum](marshaloptionsenum.md) 值。默认值是 **adMarshalAll**。</span><span class="sxs-lookup"><span data-stu-id="6a93d-p101">Sets or returns a [MarshalOptionsEnum](marshaloptionsenum.md) value. The default value is **adMarshalAll**.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a93d-108">注解</span><span class="sxs-lookup"><span data-stu-id="6a93d-108">Remarks</span></span>

<span data-ttu-id="6a93d-109">使用客户端[Recordset](recordset-object-ado.md)时, 已在客户端上修改的记录将通过一种称为封送的技术写回到中间层或 web 服务器, 这是在各个线程之间打包和发送接口方法参数的过程进程边界。</span><span class="sxs-lookup"><span data-stu-id="6a93d-109">When using a client-side [Recordset](recordset-object-ado.md), records that have been modified on the client are written back to the middle tier or web server through a technique called marshaling, the process of packaging and sending interface method parameters across thread or process boundaries.</span></span> <span data-ttu-id="6a93d-110">当修改的远程数据被封送回中间层或 web 服务器时, 设置**MarshalOptions**属性可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="6a93d-110">Setting the **MarshalOptions** property can improve performance when modified remote data is marshaled for updating back to the middle tier or web server.</span></span>

<span data-ttu-id="6a93d-111">**远程数据服务使用情况**此属性仅在客户端**Recordset**上使用。</span><span class="sxs-lookup"><span data-stu-id="6a93d-111">**Remote Data Service Usage**This property is used only on a client-side **Recordset**.</span></span>

