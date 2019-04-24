---
title: Outlook PIA 的体系结构
TOCTitle: Architecture of the Outlook PIA
ms:assetid: 89577d14-e6e2-4270-8e72-b0adba378667
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb646255(v=office.15)
ms:contentKeyID: 55119777
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 37ecad42b08b96d79d96d62f98e27913a0309971
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336524"
---
# <a name="architecture-of-the-outlook-pia"></a>Outlook PIA 体系结构

Outlook 主互操作程序集 (PIA) 完全支持使用托管代码对 Outlook 对象模型进行开发。 但是，当您第一次在对象浏览器中查看 PIA 时，您或许会感到惊讶，因为 PIA 包含很多多余的接口，而且，并非对象的所有方法、属性和事件成员都由同一对象接口所公开。 本节中的主题介绍有关如何访问代码中的对象成员，以及在何处查找有关对象、方法、属性和事件的相关帮助等指导性内容。

## <a name="in-this-section"></a>本节内容

|主题|说明|
|:----|:----------|
|[将 Outlook PIA 与对象模型相关联](relating-the-outlook-pia-with-the-object-model.md) |介绍了基于 COM 的 Outlook 对象模型中的对象和成员如何映射到 PIA 中的相应托管接口和类。|
|[Outlook PIA 中的对象](objects-in-the-outlook-pia.md) |介绍映射到 COM 对象的典型 .NET 接口、类和委派，以及如何访问 PIA 中的对象。|
|[Outlook PIA 中的方法和属性](methods-and-properties-in-the-outlook-pia.md) |介绍了如何使用 PIA 访问托管代码中对象的方法和属性。|
|[Outlook PIA 中的事件](events-in-the-outlook-pia.md) |介绍了 PIA 中与事件相关的接口、委托和接收器帮助程序类。|

## <a name="see-also"></a>另请参阅

- [设置以使用 Outlook PIA](setting-up-to-use-the-outlook-pia.md)
- [使用 Outlook PIA 开发托管 Outlook 加载项](developing-managed-outlook-add-ins-using-the-outlook-pia.md)
- [我如何...（Outlook 2013 PIA 参考）](how-do-i-outlook-2013-pia-reference.md)

