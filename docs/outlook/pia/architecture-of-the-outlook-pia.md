---
title: Outlook PIA 的体系结构
TOCTitle: Architecture of the Outlook PIA
ms:assetid: 89577d14-e6e2-4270-8e72-b0adba378667
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb646255(v=office.15)
ms:contentKeyID: 55119777
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 759e01b7ea032f53e3afeeaccaff687afc3735b3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406146"
---
# <a name="architecture-of-the-outlook-pia"></a><span data-ttu-id="b9b90-102">Outlook PIA 体系结构</span><span class="sxs-lookup"><span data-stu-id="b9b90-102">Architecture of the Outlook PIA</span></span>

<span data-ttu-id="b9b90-103">Outlook 主互操作程序集 (PIA) 完全支持使用托管代码对 Outlook 对象模型进行开发。</span><span class="sxs-lookup"><span data-stu-id="b9b90-103">The Microsoft Outlook 2010 Primary Interop Assembly (PIA) fully supports developing against the Outlook object model in managed code.</span></span> <span data-ttu-id="b9b90-104">但是，当您第一次在对象浏览器中查看 PIA 时，您或许会感到惊讶，因为 PIA 包含很多多余的接口，而且，并非对象的所有方法、属性和事件成员都由同一对象接口所公开。</span><span class="sxs-lookup"><span data-stu-id="b9b90-104">However, when you look at the PIA in an object browser for the first time, you may be surprised by the many extra interfaces that the PIA contains, and the fact that not all method, property, and event members of an object are exposed by the same object interface.</span></span> <span data-ttu-id="b9b90-105">本节中的主题介绍有关如何访问代码中的对象成员，以及在何处查找有关对象、方法、属性和事件的相关帮助等指导性内容。</span><span class="sxs-lookup"><span data-stu-id="b9b90-105">The topics in this section describe guidelines for how to access object members in code, and where to look for help for objects, methods, properties, and events.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b9b90-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="b9b90-106">In this section</span></span>

|<span data-ttu-id="b9b90-107">主题</span><span class="sxs-lookup"><span data-stu-id="b9b90-107">Topic</span></span>|<span data-ttu-id="b9b90-108">说明</span><span class="sxs-lookup"><span data-stu-id="b9b90-108">Description</span></span>|
|:----|:----------|
|[<span data-ttu-id="b9b90-109">将 Outlook PIA 与对象模型相关联</span><span class="sxs-lookup"><span data-stu-id="b9b90-109">Relating the Outlook PIA with the Object Model</span></span>](relating-the-outlook-pia-with-the-object-model.md) |<span data-ttu-id="b9b90-110">介绍了基于 COM 的 Outlook 对象模型中的对象和成员如何映射到 PIA 中的相应托管接口和类。</span><span class="sxs-lookup"><span data-stu-id="b9b90-110">Describes how objects and members in the COM-based Outlook object model are mapped to corresponding managed interfaces and classes in the PIA.</span></span>|
|[<span data-ttu-id="b9b90-111">Outlook PIA 中的对象</span><span class="sxs-lookup"><span data-stu-id="b9b90-111">Objects in the Outlook PIA</span></span>](objects-in-the-outlook-pia.md) |<span data-ttu-id="b9b90-112">介绍映射到 COM 对象的典型 .NET 接口、类和委派，以及如何访问 PIA 中的对象。</span><span class="sxs-lookup"><span data-stu-id="b9b90-112">Describes the typical .NET interfaces, classes, and delegates that are mapped to a COM object, and describes how to access an object in the PIA.</span></span>|
|[<span data-ttu-id="b9b90-113">Outlook PIA 中的方法和属性</span><span class="sxs-lookup"><span data-stu-id="b9b90-113">Methods and Properties in the Outlook PIA</span></span>](methods-and-properties-in-the-outlook-pia.md) |<span data-ttu-id="b9b90-114">介绍了如何使用 PIA 访问托管代码中对象的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="b9b90-114">Describes how to access methods and properties of an object in managed code by using the PIA.</span></span>|
|[<span data-ttu-id="b9b90-115">Outlook PIA 中的事件</span><span class="sxs-lookup"><span data-stu-id="b9b90-115">Events in the Outlook PIA</span></span>](events-in-the-outlook-pia.md) |<span data-ttu-id="b9b90-116">介绍了 PIA 中与事件相关的接口、委托和接收器帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="b9b90-116">Describes event-related interfaces, delegates, and sink helper classes in the PIA.</span></span>|

## <a name="see-also"></a><span data-ttu-id="b9b90-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9b90-117">See also</span></span>

- [<span data-ttu-id="b9b90-118">设置以使用 Outlook PIA</span><span class="sxs-lookup"><span data-stu-id="b9b90-118">Setting Up to Use the Outlook PIA</span></span>](setting-up-to-use-the-outlook-pia.md)
- [<span data-ttu-id="b9b90-119">使用 Outlook PIA 开发托管 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="b9b90-119">Developing Managed Outlook Add-ins Using the Outlook PIA</span></span>](developing-managed-outlook-add-ins-using-the-outlook-pia.md)
- [<span data-ttu-id="b9b90-120">我如何...（Outlook 2013 PIA 参考）</span><span class="sxs-lookup"><span data-stu-id="b9b90-120">How do I... (Outlook 2013 PIA Reference)</span></span>](how-do-i-outlook-2013-pia-reference.md)
