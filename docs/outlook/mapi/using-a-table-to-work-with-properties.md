---
title: 使用表处理属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c18ed9f7-c053-4453-b0b1-06234cdfb025
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9f02da9eb1920f55acf65dfb6a503e42d4c3daf2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585421"
---
# <a name="using-a-table-to-work-with-properties"></a>使用表处理属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
从支持它们的对象和作为对表的列都提供了许多属性。 只要有可能，检索表通过这些属性。
  
呼叫[IMAPITable::SetColumns](imapitable-setcolumns.md)要包含的所有客户端所需的属性和[IMAPITable::QueryRows](imapitable-queryrows.md)检索所有表的行。 
  
以下两个通话通常足以满足检索足够的信息来显示给用户，且经常足以进行任何所需的内部处理，调用**OpenEntry**打开不必要的对象。 
  
有只有两个例外情况：
  
- 如果属性为超过 255 个字节。 * * IMAPITable * * 界面可能不会返回整个属性值，而将其截断在 255 个字节。 上述考虑此利弊权衡。 如果您要向用户显示该数据，255 个字节可能足够如注释的文本字段。 
    
- 如果您需要从表中的单个行的特定属性。 在这种情况下不需要创建一个包含永远不会将使用的属性表。 大多数情况下需要将相同的属性的所有行。
    

