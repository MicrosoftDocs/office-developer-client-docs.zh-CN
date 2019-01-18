---
title: 安装和引用 Outlook PIA
TOCTitle: Installing and referencing the Outlook PIA
ms:assetid: b1afd047-dcbb-480f-ba74-993d7d7114cb
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb646840(v=office.15)
ms:contentKeyID: 55119774
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 45584ae0a7050aa769368db518c9efcd5db9975a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718201"
---
# <a name="installing-and-referencing-the-outlook-pia"></a>安装和引用 Outlook PIA

必须先在全局程序集缓存 (GAC) 中安装 Outlook 主互操作程序集 (PIA)，然后才能将 PIA 中的信息并入 Outlook 托管加载项中。 默认情况下，当你在开发计算机上安装 Office 时，PIA 会随之自动安装。 不过，如果需要单独安装 PIA，请参阅[将计算机配置为开发 Office 解决方案](https://docs.microsoft.com/visualstudio/vsto/configuring-a-computer-to-develop-office-solutions?view=vs-2017)。


> [!NOTE] 
> 必须是开发计算机上的管理员，才能安装 Office PIA。

安装完成后，若要使用 Visual Studio 创建托管项目，可以添加对 Microsoft Outlook 15.0 对象库组件的引用。 随后，在对象浏览器中的 **Microsoft.Office.Interop.Outlook** 命名空间下，便会发现 PIA 中有名称与 Outlook 对象模型中对象对应的托管接口。

## <a name="see-also"></a>另请参阅

- [安装 Office 主互操作程序集](https://docs.microsoft.com/visualstudio/vsto/how-to-install-office-primary-interop-assemblies?view=vs-2017)
- [Outlook PIA 体系结构](architecture-of-the-outlook-pia.md)

