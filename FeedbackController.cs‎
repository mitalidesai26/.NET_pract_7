using Microsoft.AspNetCore.Mvc;
using FeedbackManagementMVC.Models;

namespace FeedbackManagementMVC.Controllers
{
    public class FeedbackController : Controller
    {
        // Demo storage: feedback is kept in memory and resets when the app restarts.
        private static readonly List<Feedback> feedbackList = new();
        private static int nextId = 1;

        public IActionResult Index()
        {
            return View(feedbackList);
        }

        [HttpPost]
        [ValidateAntiForgeryToken]
        public IActionResult Create(Feedback feedback)
        {
            if (ModelState.IsValid)
            {
                feedback.Id = nextId++;
                feedbackList.Add(feedback);
                return RedirectToAction(nameof(Index));
            }

            return View(nameof(Index), feedbackList);
        }
    }
}
