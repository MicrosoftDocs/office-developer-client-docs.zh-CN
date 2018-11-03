---
title: 在 IIS 上配置虚拟服务器
TOCTitle: Configuring virtual servers on IIS
ms:assetid: 0a8057a2-c90b-d0b5-21c8-5343e80708ce
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248837(v=office.15)
ms:contentKeyID: 48543154
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f8ab3bf8e6ffec2b72744d3abacceb4725c98b02
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946725"
---
# <a name="configuring-virtual-servers-on-iis"></a><span data-ttu-id="86a86-102">在 IIS 上配置虚拟服务器</span><span class="sxs-lookup"><span data-stu-id="86a86-102">Configuring virtual servers on IIS</span></span>

<span data-ttu-id="86a86-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="86a86-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="86a86-104">当在 Internet 信息服务 4.0 中创建虚拟服务器时，还需要额外执行下面的两个步骤，以便将虚拟服务器配置为与 RDS 一起工作：</span><span class="sxs-lookup"><span data-stu-id="86a86-104">When creating virtual servers in Internet Information Services 4.0, the following two extra steps are needed in order to configure the virtual server to work with RDS:</span></span>

1.  <span data-ttu-id="86a86-105">当设置服务器时，请选择"Allow Execute Access"。</span><span class="sxs-lookup"><span data-stu-id="86a86-105">When setting up the server, check "Allow Execute Access."</span></span>

2.  <span data-ttu-id="86a86-106">将 msadcs.dll 移到*vroot*\\msadc，其中 *，vroot*是虚拟服务器的主目录。</span><span class="sxs-lookup"><span data-stu-id="86a86-106">Move msadcs.dll to *vroot*\\msadc, where *vroot* is the home directory of your virtual server.</span></span>

