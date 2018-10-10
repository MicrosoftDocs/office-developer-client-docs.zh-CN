---
title: MarshalOptions 属性 (ADO)
TOCTitle: MarshalOptions Property (ADO)
ms:assetid: dc9c4e94-0725-210d-8251-079054541142
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250118(v=office.15)
ms:contentKeyID: 48548143
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f290f2f4fb4820fb01d3a63aef7bcfbfa7c1f035
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468075"
---
# <a name="marshaloptions-property-ado"></a><span data-ttu-id="6c488-102">MarshalOptions 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="6c488-102">MarshalOptions Property (ADO)</span></span>


<span data-ttu-id="6c488-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6c488-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6c488-104">指示哪些记录要封送回服务器。</span><span class="sxs-lookup"><span data-stu-id="6c488-104">Indicates which records are to be marshaled back to the server.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="6c488-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="6c488-105">Settings And Return Values</span></span>

<span data-ttu-id="6c488-p101">设置或返回一个 [MarshalOptionsEnum](marshaloptionsenum.md) 值。默认值是 **adMarshalAll** 。</span><span class="sxs-lookup"><span data-stu-id="6c488-p101">Sets or returns a [MarshalOptionsEnum](marshaloptionsenum.md) value. The default value is **adMarshalAll**.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c488-108">备注</span><span class="sxs-lookup"><span data-stu-id="6c488-108">Remarks</span></span>

<span data-ttu-id="6c488-p102">使用客户端 [Recordset](recordset-object-ado.md) 时，已在客户端上修改的记录通过名为封送的技术写回中间层或 Web 服务器，封送是指跨线程或进程边界打包和发送接口方法参数的过程。当已修改的远程数据通过封送更新回中间层或 Web 服务器时，设置 **MarshalOptions** 属性可提高性能。</span><span class="sxs-lookup"><span data-stu-id="6c488-p102">When using a client-side [Recordset](recordset-object-ado.md), records that have been modified on the client are written back to the middle tier or Web server through a technique called marshaling, the process of packaging and sending interface method parameters across thread or process boundaries. Setting the **MarshalOptions** property can improve performance when modified remote data is marshaled for updating back to the middle tier or Web server.</span></span>

<span data-ttu-id="6c488-111">**远程数据服务用法**此属性只能在客户端**Recordset**上使用。</span><span class="sxs-lookup"><span data-stu-id="6c488-111">**Remote Data Service Usage**This property is used only on a client-side **Recordset**.</span></span>

