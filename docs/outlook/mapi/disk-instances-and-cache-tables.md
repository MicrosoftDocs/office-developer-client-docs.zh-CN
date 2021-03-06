---
title: 磁盘实例和缓存表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d556ff4d-e2f3-4c83-a93f-b1bfda5abc8c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4f0b66476b1ab3d149b6f7e7b8171de7a509b597
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436753"
---
# <a name="disk-instances-and-cache-tables"></a>磁盘实例和缓存表

**适用于**：Outlook 2013 | Outlook 2016 
  
若要激活表单，其可执行文件必须在用户计算机上可用。 如果它们不可用，则必须从表单库复制到本地磁盘。 为此，默认表单管理器在用户的 Windows 目录中创建一个子目录，以包含表单的可执行 (。EXES。HLPs) 。 此目录称为表单的磁盘实例。
  
默认表单管理器维护所有磁盘实例的表，以便如果存在磁盘实例，则无需将文件从表单库复制到用户的磁盘即可使用。 磁盘实例表作为最不经常使用的缓存进行管理。 如果需要新的磁盘实例，则它将复制到用户的计算机，以替换最不常用的磁盘实例。 然后更新磁盘实例缓存表以反映最新配置。 磁盘缓存的大小是一个用户可配置的选项，允许用户平衡速度与可用磁盘容量。
  
除了磁盘实例缓存之外，默认表单管理器还维护一个正在运行的实例表，该表列出用户计算机上所有正在运行的表单服务器实例。 这将使用 MAPI 使空闲的表单实例在不可见状态中运行，直到激活该表单服务器的邮件类的表单。 换句话说，可以将表单服务器缓存在 RAM 中，以最大限度地减少表单的可执行文件必须位于表单库中，并且必须从磁盘或网络加载到内存中的时间。 与磁盘实例缓存一样，正在运行的实例缓存以最不常用的方式运行，以便从缓存中清除正在运行的 表单实例，为另一个表单实例。 在搜索表单库之前，先搜索表单服务器的运行实例，然后再搜索此缓存。
  
> [!NOTE]
> 在用户工作站上安装表单时，默认表单管理器会显示一个进度指示器，允许用户取消操作。 如果用户与表单服务器的可执行文件的连接位于低带宽网络中，这将特别有用。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 表单](mapi-forms.md)

