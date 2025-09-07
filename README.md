<!DOCTYPE html>
<html lang="en">
<head>
<form
  action="https://formspree.io/f/mvgbdole"
  method="POST"
>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Client Scope & Sizing Questionnaire</title>
  <style>
    body { font-family: Arial, sans-serif; line-height: 1.6; margin: 20px; background: #f9f9f9; }
    h1 { text-align: center; color: #134D33; }
    h2 { background: #134D33; color: white; padding: 10px; border-radius: 5px; }
    label { display: block; margin-top: 10px; font-weight: bold; }
    input, select, textarea { width: 100%; padding: 8px; margin-top: 5px; border: 1px solid #ccc; border-radius: 4px; }
    textarea { height: 80px; }
    button { margin-top: 20px; padding: 10px 20px; background: #006400; color: #fff; border: none; border-radius: 5px; cursor: pointer; }
    button:hover { background: #004d00; }
    .hidden { display: none; }
    .module-block { margin: 10px 0 20px 20px; padding: 10px; background: #eef9ee; border-radius: 5px; border: 1px solid #006400; }
    .logo { display: block; margin: 0 auto 20px auto; max-width: 200px; }
  </style>
</head>
<body>
  <!-- Company Logo at the top -->
  <img src="company-logo.jpg" alt="Company Logo" class="logo">

  <h1>Client Scope & Sizing Questionnaire</h1>
  <form action="https://formspree.io/f/yourFormID" method="POST">

    <!-- Section 1 -->
    <h2>Section 1: Company & Contact Details</h2>
    <label>Company Name *</label>
    <input type="text" name="company_name" required>
    
    <label>Industry / Sector</label>
    <input type="text" name="industry">

    <label>Headquarters Location</label>
    <input type="text" name="hq_location">

    <label>Contact Person Name *</label>
    <input type="text" name="contact_name" required>

    <label>Contact Email *</label>
    <input type="email" name="contact_email" required>

    <label>Contact Phone</label>
    <input type="text" name="contact_phone">

    <!-- Section 2 -->
    <h2>Section 2: Modules & Requirements</h2>
    <p>Select the Modules You Need:</p>

    <!-- Reusable Module Template -->
    <script>
      function createModule(moduleId, moduleName, allowSpecify = false) {
        document.write(`
          <label><input type="checkbox" onchange="toggleModule('${moduleId}')"> ${moduleName}</label>
          <div id="${moduleId}" class="module-block hidden">
            ${allowSpecify ? `<input type="text" name="${moduleId}_name" placeholder="Please specify">` : ""}
            <label>Customization Preference (${moduleName})</label>
            <select name="${moduleId}_customization" onchange="toggleCustomization('${moduleId}', this.value)">
              <option value="As-Is">As-Is</option>
              <option value="Customization Needed">Customization Needed</option>
            </select>
            <div id="${moduleId}_custom_details" class="hidden">
              <label>Priority (${moduleName})</label>
              <select name="${moduleId}_priority">
                <option value="Mandatory">Mandatory</option>
                <option value="Good to Have">Good to Have</option>
                <option value="Optional">Optional</option>
              </select>
              <label>What do you want to customize in ${moduleName}?</label>
              <textarea name="${moduleId}_custom_notes"></textarea>
            </div>
          </div>
        `);
      }
    </script>

    <!-- Module List -->
    <script>
      createModule("governance", "Governance");
      createModule("risk", "Risk Management");
      createModule("compliance", "Compliance");
      createModule("document", "Document Management");
      createModule("incident", "Incident Management");
      createModule("asset", "Asset Management");
      createModule("bcm", "Business Continuity Management");
      createModule("thirdparty", "Third-Party Risk Management");
      createModule("audit", "Audit Management");
      createModule("strategy", "Strategy Management");
      createModule("others", "Others (please specify)", true);
    </script>

    <!-- Section 3 -->
    <h2>Section 3: Users</h2>
    <label>Estimated Number of Active Users</label>
    <input type="text" name="active_users">

    <label>Estimated Number of Passive Users</label>
    <input type="text" name="passive_users">

    <!-- Section 4 -->
    <h2>Section 4: Deployment Preferences</h2>
    <label><input type="radio" name="deployment" value="Cloud"> Cloud</label>
    <label><input type="radio" name="deployment" value="On-Premises"> On-Premises</label>
    <label><input type="radio" name="deployment" value="Hybrid"> Hybrid</label>

    <!-- Section 5 -->
    <h2>Section 5: Integrations</h2>
    <label><input type="checkbox" name="integrations" value="Active Directory"> Active Directory (AD)</label>
    <label><input type="checkbox" name="integrations" value="SIEM"> SIEM Solutions</label>
    <label><input type="checkbox" name="integrations" value="Tenable"> Tenable</label>
    <input type="text" name="integrations_other" placeholder="Others (please specify)">

    <!-- Section 6 -->
    <h2>Section 6: Project Timeline</h2>
    <label>Expected Project Duration / Support Term</label>
    <select name="duration">
      <option value="2 Years">2 Years</option>
      <option value="3 Years">3 Years</option>
      <option value="5 Years">5 Years</option>
    </select>

    <label>Planned Project Start</label>
    <select name="project_start">
      <option value="This Year">This Year</option>
      <option value="Next Year">Next Year</option>
    </select>

    <!-- Section 7 -->
    <h2>Section 7: Budget</h2>
    <label>Do you have a defined budget?</label>
    <label><input type="radio" name="budget_defined" value="Yes"> Yes</label>
    <label><input type="radio" name="budget_defined" value="No"> No</label>
    <input type="text" name="budget_range" placeholder="If Yes, please specify range">

    <!-- Section 8 -->
    <h2>Section 8: Current Environment</h2>
    <label>Do you currently use any GRC / Risk / Audit solutions?</label>
    <label><input type="radio" name="current_solution" value="Yes"> Yes</label>
    <label><input type="radio" name="current_solution" value="No"> No</label>
    <input type="text" name="current_solution_details" placeholder="If Yes, please specify">

    <!-- Section 9 -->
    <h2>Section 9: Additional Notes</h2>
    <textarea name="additional_notes" placeholder="Any other comments or requirements?"></textarea>

    <button type="submit">Submit</button>
  </form>

  <script>
    function toggleModule(moduleId) {
      const section = document.getElementById(moduleId);
      section.classList.toggle("hidden");
    }

    function toggleCustomization(moduleId, value) {
      const customDiv = document.getElementById(moduleId + "_custom_details");
      if (value === "Customization Needed") {
        customDiv.classList.remove("hidden");
      } else {
        customDiv.classList.add("hidden");
      }
    }
  </script>
</body>
</html>
