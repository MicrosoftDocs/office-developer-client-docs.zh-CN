---
title: MAPI 窗体对象
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
# <a name="mapi-form-objects"></a>MAPI 窗体对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表单对象由表单服务器动态创建，以便显示特定消息并允许用户与其交互。 因此，表单对象是由表单服务器实现的 [IMAPIForm](imapiformiunknown.md) 派生的类实例化。 当客户端应用程序打开邮件时，该邮件类的窗体服务器会创建一个表单对象来处理邮件。 然后，表单对象创建其接口，并显示其中的消息属性。 窗体对象及其接口将一直保留，直到用户关闭它。 form 对象处理对邮件属性值的任何更改。 
  
此外，MAPI 表单接口还定义了一种机制，一个表单对象可以通过该机制加载和显示一系列消息。 这是一种效率机制，因为它可以避免不必要的破坏和创建邮件对象及其接口。 当邮件客户端请求加载其他邮件时，表单对象应保存对当前邮件属性的任何更改。
  
有关客户端应用程序对表单对象的角度的信息，请参阅[MAPI Custom Form Objects。](mapi-custom-form-objects.md)
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

