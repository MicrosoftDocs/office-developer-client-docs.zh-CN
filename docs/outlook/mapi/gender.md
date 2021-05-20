---
title: Gender
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f60c65e3-b55f-cb68-746e-d0a8cd862d4d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 042216df309e98f35ed0ad71742e46300ebb06da
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428646"
---
# <a name="gender"></a>Gender

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定邮件用户的性别的可能值。
  
## <a name="quick-info"></a>快速信息

```cpp
enum Gender { 
    genderMin = 0, 
    genderUnspecified = genderMin, 
    genderFemale, 
    genderMale, 
    genderCount, 
    genderMax = genderCount - 1 
}; 

```

## <a name="members"></a>成员

 _genderMin_
  
> 支持性别的不同值的最小数量。
    
 _genderUnspecified_
  
> 没有为消息传递用户指定性别。
    
 _genderFemale_
  
> 邮件用户是男性。
    
 _genderMale_
  
> 消息传送用户是男性。
    
 _genderCount_
  
> 支持性别的不同值的数量。
    
 _genderMax_
  
> 性别支持的不同值的最大数量。
    
## <a name="see-also"></a>另请参阅



[PidTagGender 规范属性](pidtaggender-canonical-property.md)

