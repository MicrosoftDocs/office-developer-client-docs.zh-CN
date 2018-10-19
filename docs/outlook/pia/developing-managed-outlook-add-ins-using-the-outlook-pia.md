---
title: 使用 Outlook PIA 开发托管 Outlook 加载项
TOCTitle: Developing managed Outlook add-ins using the Outlook PIA
ms:assetid: a779f49e-656b-4726-b0c6-37c4a6f9abd1
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb646706(v=office.15)
ms:contentKeyID: 55119781
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 6415f9afa59d73b43592d9fe64a5a61d271002a8
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406489"
---
# <a name="developing-managed-outlook-add-ins-using-the-outlook-pia"></a><span data-ttu-id="64d66-102">使用 Outlook PIA 开发托管 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="64d66-102">Developing Managed Outlook Add-ins Using the Outlook PIA</span></span>

<span data-ttu-id="64d66-103">本节中的主题介绍使用 Outlook 主互操作程序集 (PIA) 进行自定义事件处理，并列出了您在编写托管 Outlook 加载项时应注意的一些方面以避免出现常见错误。有关使用 PIA 为 Office 编写托管应用程序的更多基本信息，请参阅 [Visual Studio Tools for Office（该链接可能指向英文页面）](https://docs.microsoft.com/visualstudio/vsto/office-and-sharepoint-development-in-visual-studio?view=vs-2017)。</span><span class="sxs-lookup"><span data-stu-id="64d66-103">The topics in this section describe custom event handling using the Outlook Primary Interop Assembly (PIA) and list a few areas that you should be aware of to avoid common pitfalls when writing managed Outlook add-ins. For more basic information about writing managed applications for Office using PIA, see [Office Development in Visual Studio](https://docs.microsoft.com/visualstudio/vsto/office-and-sharepoint-development-in-visual-studio?view=vs-2017).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="64d66-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="64d66-104">In this section</span></span>

|<span data-ttu-id="64d66-105">主题</span><span class="sxs-lookup"><span data-stu-id="64d66-105">Topic</span></span>|<span data-ttu-id="64d66-106">说明</span><span class="sxs-lookup"><span data-stu-id="64d66-106">Description</span></span>|
|:----|:----------|
|[<span data-ttu-id="64d66-107">连接到自定义事件处理程序</span><span class="sxs-lookup"><span data-stu-id="64d66-107">Connecting to Custom Event Handlers</span></span>](connecting-to-custom-event-handlers.md) |<span data-ttu-id="64d66-108">介绍了定义回调方法并将它连接为 Outlook 对象的自定义事件处理程序的过程。</span><span class="sxs-lookup"><span data-stu-id="64d66-108">Describes the process of defining a callback method and connecting it as a custom event handler for an Outlook object.</span></span>|
|[<span data-ttu-id="64d66-109">托管 Outlook 加载项开发最佳做法</span><span class="sxs-lookup"><span data-stu-id="64d66-109">Best Practices in Developing Managed Outlook Add-ins</span></span>](best-practices-in-developing-managed-outlook-add-ins.md) |<span data-ttu-id="64d66-110">推荐了最佳做法，以免遇到一些常见的托管 Outlook 加载项开发问题。</span><span class="sxs-lookup"><span data-stu-id="64d66-110">Recommends practices to avoid some common problems in developing managed Outlook add-ins.</span></span>

## <a name="see-also"></a><span data-ttu-id="64d66-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64d66-111">See also</span></span>

- [<span data-ttu-id="64d66-112">设置以使用 Outlook PIA</span><span class="sxs-lookup"><span data-stu-id="64d66-112">Setting Up to Use the Outlook PIA</span></span>](setting-up-to-use-the-outlook-pia.md)
- [<span data-ttu-id="64d66-113">Outlook PIA 体系结构</span><span class="sxs-lookup"><span data-stu-id="64d66-113">Architecture of the Outlook PIA</span></span>](architecture-of-the-outlook-pia.md)
- [<span data-ttu-id="64d66-114">我如何...（Outlook 2013 PIA 参考）</span><span class="sxs-lookup"><span data-stu-id="64d66-114">How do I... (Outlook 2013 PIA reference)</span></span>](how-do-i-outlook-2013-pia-reference.md)

