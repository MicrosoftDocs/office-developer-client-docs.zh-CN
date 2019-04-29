---
title: MAPI 表单对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eb9107d9-ad5c-4264-a457-dea193597dc9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5a7c6c575f277a91a18f0d834e26d3d376613fba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404783"
---
# <a name="mapi-form-objects"></a>MAPI 表单对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
窗体对象是由窗体服务器动态创建的, 以便显示特定的邮件, 并允许用户与其进行交互。 因此, form 对象是从窗体服务器实现的[IMAPIForm](imapiformiunknown.md)派生的类的实例化。 当客户端应用程序打开邮件时, 该邮件类的窗体服务器将创建一个窗体对象来处理该邮件。 然后, 该窗体对象将创建其接口, 并在其中显示邮件的属性。 form 对象及其接口将一直保留, 直到用户关闭它。 form 对象处理对邮件属性值所做的任何更改。 
  
此外, MAPI 表单接口定义一种机制, 一个窗体对象可以通过它加载和显示一系列邮件。 这是一种高效机制, 因为它避免了不必要的邮件对象及其接口的销毁和创建。 当邮件客户端请求加载不同的邮件时, 该窗体对象应保存对当前邮件的属性所做的任何更改。
  
有关客户端应用程序的 form 对象角度的信息, 请参阅[MAPI 自定义表单对象](mapi-custom-form-objects.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

