---
title: Gender
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f60c65e3-b55f-cb68-746e-d0a8cd862d4d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7abc62938b3c33e42adedfe8ccd66e072314e333
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775023"
---
# <a name="gender"></a>Gender

  
  
**适用于**： Outlook 
  
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

## <a name="members"></a>Members

 _genderMin_
  
> 支持的性别的不同值的最小数目。
    
 _genderUnspecified_
  
> 未指定邮件用户的性别。
    
 _genderFemale_
  
> 女消息用户。
    
 _genderMale_
  
> 男性消息用户。
    
 _genderCount_
  
> 支持的性别的不同值的数目。
    
 _genderMax_
  
> 支持的性别的不同值的最大数目。
    
## <a name="see-also"></a>另请参阅



[PidTagGender 规范属性](pidtaggender-canonical-property.md)

