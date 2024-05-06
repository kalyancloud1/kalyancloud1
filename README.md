package seleniumpractice.stepdefs;

import java.util.Map;

import io.cucumber.datatable.DataTable;
import io.cucumber.java.en.Given;
import io.cucumber.java.en.Then;
import io.cucumber.java.en.When;


	public class CurrentOpeningStepdefs {
		
		private CurrentOpeningsPage currentOpeningsPage;

		public CurrentOpeningStepdefs(CurrentOpeningsPage currentOpeningsPage) {
			this.currentOpeningsPage = currentOpeningsPage;
		}
		
		@Then("verify current opening page is loaded")
		public void verify_current_opening_loaded() {
			currentOpeningsPage.waitForCurrentOpenigsHeader();
		}
		
		@When("i click on add opening")
		public void click_on_add_opening() {
			currentOpeningsPage.clickOnAddOpening();
		}
		
		@Then("verify add opening page is opened")
		public void verify_add_opening_page_opened() {
			currentOpeningsPage.waitForAddOpening();
		}
		
		@Given("the following details in opening page")
		public void given_details_in_add_opening(DataTable dataTable) {
			Map<String, String> data = dataTable.asMap();
			currentOpeningsPage.enterDetailsInAddOpening(data);
			
		}
		
		@When("i click on save button in add project page")
		public void click _on_save_button() {
			currentOpeningsPage.clickOnSaveButton();
		}
		
		@Then("project should be added successfully")
		public void project_added_successfully() {
			currentOpeningsPage.assertSuccessMessage();
		}
		
		@Given("openingname in current openings search")
		public void projectname_in_manage_projects() {
			currentOpeningsPage.searchOpening();
		}
		
		@Then("verify created openingname is visible in list")
		public void verify_created_openingname_is_visible_in_list() {
			currentOpeningsPage.assertCreatedOpening
			InList();
		}
		
		@When("i click on edit icon for the first record in the list")
		public void i_click_on_edit_icon_for_the_first_record_in_the_list() {
			manageProjectsPage.clickOnFirstRowEditIcon();
		}
		
		@When("i click on delete icon for the first record in the list")
		public void i_click_on_delete_icon_for_the_first_record_in_the_list() {
			manageProjectsPage.clickOnFirstRowDeleteIcon();
		}
		
		@Then("verify edit project page is opened")
		public void verify_edit_project_page_is_opened() {
			manageProjectsPage.waitForEditProject();
		}
		
		@Then("verify saved project details")
		public void verify_saved_project_details() {
			manageProjectsPage.assertCreatedProjectDetails();
		}
		
		@When("i click on update button in edit project page")
		public void click_on_update_button() {
			manageProjectsPage.clickOnUpdateButton();
		}
		
		@Then("project should be updated successfully")
		public void project_updated_successfully() {
			manageProjectsPage.assertUpdateSuccessMessage();
		}
		
		@Then("delete confirmation should be visible")
		public void delete_confirmation_should_be_visible() {
			manageProjectsPage.waitForDeleteConfirmationModal();
		}
		
		@When("i click on yes in delete confirmation")
		public void i_click_on_yes_in_delete_confirmation() {
			manageProjectsPage.clickOnYesInConfirmModal();
		}
		
		@Then("project should be deleted successfully")
		public void project_deleted_successfully() {
			manageProjectsPage.assertDeleteSuccessMessage();
		}
		
		@Then("verify projectname is not available in list page")
		public void verify_projectname_is_not_available_in_list_page() {
			manageProjectsPage.assertProjectRecordNotExistInListPage();
		}
	}

		
