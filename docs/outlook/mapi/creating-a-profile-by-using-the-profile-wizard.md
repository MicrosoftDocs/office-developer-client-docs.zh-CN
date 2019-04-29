---
title: 使用配置文件向导创建配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4b611818-f99f-43a2-9f6b-1aa5b9564d1d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a93cfb05d8abfffc9f55a7ea48efc3c3451dddbb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411734"
---
# <a name="creating-a-profile-by-using-the-profile-wizard"></a>使用配置文件向导创建配置文件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
配置文件向导是一项 MAPI 功能, 它使用户能够以尽可能最简单的方式创建配置文件。 配置文件向导显示一系列对话框, 提示用户选择邮件服务并为几个最基本的配置属性输入值。 对于大多数其他必需的属性, 配置文件向导使用提供的默认值。 若要调用配置文件向导, 请调用**LaunchWizard**, 它是基于[LAUNCHWIZARDENTRY](launchwizardentry.md)原型的函数。 
  
用户只能将这些邮件服务和服务提供程序添加到支持配置文件向导的新配置文件。 由于每个邮件服务可能需要比配置文件向导可以处理的属性数目更多的属性, 请注意, 如果使用此方法, 则一个或多个选定的服务或提供程序可能未完全配置。
  

