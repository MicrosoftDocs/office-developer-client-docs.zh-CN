---
title: 在 IIS 上配置虚拟服务器
TOCTitle: Configuring Virtual Servers on IIS
ms:assetid: 0a8057a2-c90b-d0b5-21c8-5343e80708ce
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248837(v=office.15)
ms:contentKeyID: 48543154
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7408e2dc10a5e47b298b77a9244477b16bca3ff1
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879240"
---
# <a name="configuring-virtual-servers-on-iis"></a>在 IIS 上配置虚拟服务器


**适用于**： Access 2013、 Office 2013

当在 Internet 信息服务 4.0 中创建虚拟服务器时，还需要额外执行下面的两个步骤，以便将虚拟服务器配置为与 RDS 一起工作：

1.  当设置服务器时，请选择"Allow Execute Access"。

2.  将 msadcs.dll 移到*vroot*\\msadc，其中 *，vroot*是虚拟服务器的主目录。

