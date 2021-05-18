---
title: 使用 GetProps 和 SetProps 获取并设置属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 309d2b3d-dc71-4222-b293-4bfc467b5429
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7d11f69c6da8560f5879ebc38498d852486bed8b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299396"
---
# <a name="getting-and-setting-properties-with-getprops-and-setprops"></a>使用 GetProps 和 SetProps 获取并设置属性
 
**适用于**：Outlook 2013 | Outlook 2016 
  
尽可能尝试使用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法检索或修改属性。 除非使用的属性非常大，否则这些方法应该足够用。 另一种替代方法是使用 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 接口从流读取或写入流。 流可以成功处理非常大的属性，但它们对资源的消耗更大，因为它们需要 COM 库。 仅在调用 **IMAPIProp：：GetProps** 或 **IMAPIProp：：SetProps 失败后，才使用** **IStream** 接口。 
  

