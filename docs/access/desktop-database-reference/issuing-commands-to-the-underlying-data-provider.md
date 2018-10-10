---
title: 向基础数据提供程序发出命令
TOCTitle: Issuing Commands to the Underlying Data Provider
ms:assetid: 9d8ef3f3-d93c-af67-3114-d2c36c78a802
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249716(v=office.15)
ms:contentKeyID: 48546626
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5083f339860e0b28b43e2ceefeaf2cdd1de4b660
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466606"
---
# <a name="issuing-commands-to-the-underlying-data-provider"></a><span data-ttu-id="a09f4-102">向基础数据提供程序发出命令</span><span class="sxs-lookup"><span data-stu-id="a09f4-102">Issuing Commands to the Underlying Data Provider</span></span>


<span data-ttu-id="a09f4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a09f4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a09f4-104">任何不以 SHAPE 开头的命令都将传递到数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="a09f4-104">Any command that does not begin with SHAPE is passed through to the data provider.</span></span> <span data-ttu-id="a09f4-105">这等价于以"SHAPE {provider command}"的形式发出 Shape 命令。</span><span class="sxs-lookup"><span data-stu-id="a09f4-105">This is equivalent to issuing a shape command in the form "SHAPE {provider command}".</span></span> <span data-ttu-id="a09f4-106">这些命令执行*不*需要生成**Recordset**。</span><span class="sxs-lookup"><span data-stu-id="a09f4-106">These commands do *not* have to produce a **Recordset**.</span></span> <span data-ttu-id="a09f4-107">例如，假如数据提供程序支持 DROP TABLE，则"SHAPE {DROP TABLE MyTable}"是完全有效的 Shape 命令。</span><span class="sxs-lookup"><span data-stu-id="a09f4-107">For instance, "SHAPE {DROP TABLE MyTable} is a perfectly valid shape command, assuming the data provider supports DROP TABLE.</span></span>

<span data-ttu-id="a09f4-108">此功能允许正常提供程序命令和 Shape 命令共享相同的连接和事务。</span><span class="sxs-lookup"><span data-stu-id="a09f4-108">This capability allows both normal provider commands and shape commands to share the same connection and transaction.</span></span>

