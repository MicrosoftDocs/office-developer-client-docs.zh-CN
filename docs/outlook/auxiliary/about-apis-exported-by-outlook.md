---
title: 有关 outlook 导出的 Api
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 7b251308-70ff-a1ec-e968-9d5993909505
description: Outlook 将导出下列定义、 数据结构、 函数和接口原本供内部使用，但现已公开面向大众的文章。
ms.openlocfilehash: 0ed68b6c1b8082ee5cc22deb96333a0bd4d29390
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316979"
---
# <a name="about-apis-exported-by-outlook"></a>有关 outlook 导出的 Api

Outlook 将导出下列定义、 数据结构、 函数和接口原本供内部使用，但现已公开面向大众的文章。
  
### <a name="definitions"></a>定义
  
- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)
    
### <a name="data-structures"></a>数据结构
  
- [TZDEFINITION](tzdefinition.md)
    
- [TZREG](tzreg.md)
    
- [TZRULE](tzrule.md)
    
### <a name="functions"></a>函数
  
- [HrCreateApptRebaser](hrcreateapptrebaser.md)
    
- [HrProcessConvActionForSentItem](hrprocessconvactionforsentitem.md)
    
- [RebaseTaskComplete](rebasetaskcomplete.md)
    
- [RebaseTaskProgress](rebasetaskprogress.md)
    
### <a name="interfaces"></a>接口
  
- [IOlkApptRebaser](iolkapptrebaser.md)
    
### <a name="events"></a>活动
  
- [可用的事件和其 dispid （Outlook 导出的 Api）](available-events-and-their-dispids-outlook-exported-apis.md)
    
此外，使用的调度标识符、 **dispidFDirty** 和 **dispidShowSenderPhoto**，您可以实现以下任务：
  
- [确定某个 Outlook 项目是否已修改但未保存（Outlook 辅助参考）](how-to-determine-if-outlook-item-has-been-modified-but-not-saved.md)
    
- [指定是否要在 Outlook（Outlook 辅助参考）中显示联系人的图片](https://msdn.microsoft.com/library/office/gg262879.aspx)
    

