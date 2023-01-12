package com.skilldistillery.jobsearch.entities;

import static org.junit.jupiter.api.Assertions.*;

import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.Persistence;

import org.junit.jupiter.api.AfterAll;
import org.junit.jupiter.api.AfterEach;
import org.junit.jupiter.api.BeforeAll;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

class UserTest {
	
	private static EntityManagerFactory emf;
	private EntityManager em;
	private User user;

	@BeforeAll
	static void setUpBeforeClass() throws Exception {
	emf = Persistence.createEntityManagerFactory("JPAOpenOffice");
	}

	@AfterAll
	static void tearDownAfterClass() throws Exception {
		emf.close();
	}

	@BeforeEach
	void setUp() throws Exception {
		em = emf.createEntityManager();
		user = em.find(User.class, 1);
	}

	@AfterEach
	void tearDown() throws Exception {
		em.close();
	}

	@Test
	void test_user_password_id_and_role() {
		assertNotNull(user);
		assertEquals(1, user.getId());
		assertEquals("openadmin", user.getPassword());
		assertTrue( user.isRole());
	}

	@Test
	void test_user_firstName_and_lastName() {
		assertNotNull(user);
		assertEquals("Johnny", user.getFirstName());
		assertEquals("Doughboy", user.getLastName());
	}
	
	@Test
	void test_User_Article_one_to_many_mapping() {
		assertNotNull(user);
		assertTrue(user.getArticles().size() > 0);
	}
	
	@Test
	void test_User_Company_many_to_many_mapping() {
		assertNotNull(user);
		assertTrue(user.getCompanies().size() > 0);
	}

	@Test
	void test_User_CompanyReview_one_to_many_mapping() {
		assertNotNull(user);
		assertTrue(user.getReviews().size() > 0);
	}
	@Test
	void test_User_interview_one_to_many_mapping() {
		assertNotNull(user);
		assertTrue(user.getInterviews().size() > 0);
	}

}
