---
title: 获取和设置与 GetProps SetProps 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 309d2b3d-dc71-4222-b293-4bfc467b5429
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5751dc8b06d40b9f07a39f05868c328d64c27762
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775045"
---
# <a name="getting-and-setting-properties-with-getprops-and-setprops"></a>获取和设置与 GetProps SetProps 属性
 
**适用于**： Outlook 
  
只要有可能，尝试检索或使用[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPIProp::SetProps](imapiprop-setprops.md)方法修改的属性。 除非您正在使用该属性是非常大，这些方法应已足够。 其他替代方法是从读取或写入到[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口的流。 流可以成功处理非常大的属性，但它们是更高版本耗尽资源，因为它们需要的 COM 库。 仅在您调用**IMAPIProp::GetProps**或**IMAPIProp::SetProps**失败后，请使用**IStream**接口。 
  

