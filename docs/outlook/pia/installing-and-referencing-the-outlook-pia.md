---
title: 安装和引用 Outlook PIA
TOCTitle: Installing and referencing the Outlook PIA
ms:assetid: b1afd047-dcbb-480f-ba74-993d7d7114cb
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb646840(v=office.15)
ms:contentKeyID: 55119774
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 42e79fcd6cf9575f43722d7ba467b028ef6c3e16
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405509"
---
# <a name="installing-and-referencing-the-outlook-pia"></a><span data-ttu-id="93cee-102">安装和引用 Outlook PIA</span><span class="sxs-lookup"><span data-stu-id="93cee-102">Installing and Referencing the Outlook PIA</span></span>

<span data-ttu-id="93cee-103">必须先在全局程序集缓存 (GAC) 中安装 Outlook 主互操作程序集 (PIA)，然后才能将 PIA 中的信息并入 Outlook 托管加载项中。</span><span class="sxs-lookup"><span data-stu-id="93cee-103">You must first install the Outlook Primary Interop Assembly (PIA) in the Global Assembly Cache (GAC) before you can incorporate information from the PIA in an Outlook managed add-in.</span></span> <span data-ttu-id="93cee-104">默认情况下，当你在开发计算机上安装 Office 时，PIA 会随之自动安装。</span><span class="sxs-lookup"><span data-stu-id="93cee-104">By default, the PIA is installed automatically when you install Office on the development computer.</span></span> <span data-ttu-id="93cee-105">不过，如果需要单独安装 PIA，请参阅[将计算机配置为开发 Office 解决方案](https://docs.microsoft.com/visualstudio/vsto/configuring-a-computer-to-develop-office-solutions?view=vs-2017)。</span><span class="sxs-lookup"><span data-stu-id="93cee-105">However, if you need to install the PIA separately, see [Configure a computer to develop Office solutions](https://docs.microsoft.com/visualstudio/vsto/configuring-a-computer-to-develop-office-solutions?view=vs-2017).</span></span>


> [!NOTE] 
> <span data-ttu-id="93cee-106">必须是开发计算机上的管理员，才能安装 Office PIA。</span><span class="sxs-lookup"><span data-stu-id="93cee-106">You must be an administrator on the development computer to install the Office PIAs.</span></span>

<span data-ttu-id="93cee-107">安装完成后，若要使用 Visual Studio 创建托管项目，可以添加对 Microsoft Outlook 15.0 对象库组件的引用。</span><span class="sxs-lookup"><span data-stu-id="93cee-107">After installation, if you are using Visual Studio to create the managed project, you can add a reference to the Microsoft Outlook 14.0 Object Library component. Subsequently, in the object browser, under the Microsoft.Office.Interop.Outlook namespace, you can see managed interfaces in the PIA that have names corresponding to objects in the Outlook object model.</span></span> <span data-ttu-id="93cee-108">随后，在对象浏览器中的 **Microsoft.Office.Interop.Outlook** 命名空间下，便会发现 PIA 中有名称与 Outlook 对象模型中对象对应的托管接口。</span><span class="sxs-lookup"><span data-stu-id="93cee-108">In the object browser, under the namespace **Microsoft.Office.Interop.Outlook**, you can see managed interfaces that have names corresponding to objects in the Outlook object model.</span></span>

## <a name="see-also"></a><span data-ttu-id="93cee-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93cee-109">See also</span></span>

- [<span data-ttu-id="93cee-110">安装 Office 主互操作程序集</span><span class="sxs-lookup"><span data-stu-id="93cee-110">Install Office primary interop assemblies</span></span>](https://docs.microsoft.com/visualstudio/vsto/how-to-install-office-primary-interop-assemblies?view=vs-2017)
- [<span data-ttu-id="93cee-111">Outlook PIA 体系结构</span><span class="sxs-lookup"><span data-stu-id="93cee-111">Architecture of the Outlook PIA</span></span>](architecture-of-the-outlook-pia.md)
