# freecodecamp-relational-database-celestial
#This is a project from freecodecamp

 --
-- PostgreSQL database dump
--

-- Dumped from database version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)
-- Dumped by pg_dump version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

DROP DATABASE universe;
--
-- Name: universe; Type: DATABASE; Schema: -; Owner: freecodecamp
--

CREATE DATABASE universe WITH TEMPLATE = template0 ENCODING = 'UTF8' LC_COLLATE = 'C.UTF-8' LC_CTYPE = 'C.UTF-8';


ALTER DATABASE universe OWNER TO freecodecamp;

\connect universe


SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

SET default_tablespace = '';

SET default_table_access_method = heap;

REATE TABLE public.galaxy (
    galaxy_id integer NOT NULL,
    name character varying(255),
    description text,
    has_life boolean NOT NULL,
    is_spherical boolean NOT NULL,
    age_in_millions integer,
    distance_in_miles integer,
    multiverses numeric,
    f_id integer NOT NULL
);


ALTER TABLE public.galaxy OWNER TO freecodecamp;


--
-- Name: galaxy_foreign_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_foreign_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_foreign_id_seq OWNER TO freecodecamp;


--
-- Name: galaxy_foreign_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_foreign_id_seq OWNED BY public.galaxy.f_id;


--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_galaxy_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_galaxy_id_seq OWNER TO freecodecamp;


--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_galaxy_id_seq OWNED BY public.galaxy.galaxy_id;


--
-- Name: meteor; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.meteor (
    meteor_id integer NOT NULL,
    name character varying(255),
    description text,
    has_life boolean NOT NULL,
    is_spherical boolean,
    age integer,
    distance integer,
    multiverse numeric,
    f_id integer NOT NULL
);


ALTER TABLE public.meteor OWNER TO freecodecamp;

--
-- Name: meteor_foreign_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.meteor_foreign_id_seq OWNED BY public.meteor.f_id;


--
-- Name: meteor_meteor_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.meteor_meteor_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.meteor_meteor_id_seq OWNER TO freecodecamp;

--
-- Name: meteor_meteor_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.meteor_meteor_id_seq OWNED BY public.meteor.meteor_id;


--
-- Name: moon; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.moon (
    moon_id integer NOT NULL,
    name character varying(255),
    description text,
    has_life boolean NOT NULL,
    is_spherical boolean NOT NULL,
    age integer,
    distance integer,
    multiverse numeric,
    f_id integer NOT NULL
);


ALTER TABLE public.moon OWNER TO freecodecamp;

--
-- Name: moon_foreign_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.moon_foreign_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.moon_foreign_id_seq OWNER TO freecodecamp; something next

--
-- Name: moon_foreign_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.moon_foreign_id_seq OWNED BY public.moon.f_id;


--
-- Name: moon_moon_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.moon_moon_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.moon_moon_id_seq OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.moon_moon_id_seq OWNED BY public.moon.moon_id;


--
-- Name: planet; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.planet (
    planet_id integer NOT NULL,
    name_of_planet character varying(255),
    description_of_planet text,
    has_life_or_not boolean NOT NULL,
    is_spherical_or_not boolean NOT NULL,
    age integer,
    distance integer,
    multiverse numeric,
    f_id integer NOT NULL
);


ALTER TABLE public.planet OWNER TO freecodecamp;

--
-- Name: planet_foreign_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.planet_foreign_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.planet_foreign_id_seq OWNER TO freecodecamp;

--
-- Name: planet_foreign_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.planet_foreign_id_seq OWNED BY public.planet.f_id;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.planet_planet_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.planet_planet_id_seq OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.planet_planet_id_seq OWNED BY public.planet.planet_id;

--
-- Name: star; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.star (
    star_id integer NOT NULL,
    name_of_thing character varying(255),
    description_of_thing text,
    has_life_or_not boolean NOT NULL,
    is_spherical_or_not boolean NOT NULL,
    age_of_thing integer,
    distance_of_thing integer,
    multiverse_or_not numeric,
    f_id integer NOT NULL
);


ALTER TABLE public.star OWNER TO freecodecamp;

--
-- Name: star_foreign_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.star_foreign_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.star_foreign_id_seq OWNER TO freecodecamp;

--
-- Name: star_foreign_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.star_foreign_id_seq OWNED BY public.star.f_id;


--
-- Name: star_star_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.star_star_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.star_star_id_seq OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.star_star_id_seq OWNED BY public.star.star_id;


--
-- Name: galaxy galaxy_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy ALTER COLUMN galaxy_id SET DEFAULT nextval('public.galaxy_galaxy_id_seq'::regclass);


--
-- Name: galaxy f_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--


ALTER TABLE ONLY public.galaxy ALTER COLUMN f_id SET DEFAULT nextval('public.galaxy_foreign_id_seq'::regclass);


--
-- Name: meteor meteor_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.meteor ALTER COLUMN meteor_id SET DEFAULT nextval('public.meteor_meteor_id_seq'::regclass);


--
-- Name: meteor f_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.meteor ALTER COLUMN f_id SET DEFAULT nextval('public.meteor_foreign_id_seq'::regclass);


--
-- Name: moon moon_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon ALTER COLUMN moon_id SET DEFAULT nextval('public.moon_moon_id_seq'::regclass);


--
-- Name: moon f_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon ALTER COLUMN f_id SET DEFAULT nextval('public.moon_foreign_id_seq'::regclass);


--
-- Name: planet planet_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet ALTER COLUMN planet_id SET DEFAULT nextval('public.planet_planet_id_seq'::regclass);


--
-- Name: planet f_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet ALTER COLUMN f_id SET DEFAULT nextval('public.planet_foreign_id_seq'::regclass);


--
-- Name: star star_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star ALTER COLUMN star_id SET DEFAULT nextval('public.star_star_id_seq'::regclass);


--
-- Name: star f_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star ALTER COLUMN f_id SET DEFAULT nextval('public.star_foreign_id_seq'::regclass);


--
-- Data for Name: galaxy; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.galaxy VALUES (1, 'Milky Way', 'The one everyone knows', false, true, 7434, 93, 3, 1);
INSERT INTO public.galaxy VALUES (2, 'Andromeda', 'This another famous one', true, false, 742, 924, 23, 2);
INSERT INTO public.galaxy VALUES (3, 'Misser 96', 'This is a new one I just found out about', false, true, 45, 323, 2, 33);
INSERT INTO public.galaxy VALUES (4, 'Black Eye', 'The major swirl in the middle', true, true, 943, 71, 633, 45);
INSERT INTO public.galaxy VALUES (5, 'Tadpole', 'The straight shooter no chaser', true, false, 88, 37, 63, 45);
INSERT INTO public.galaxy VALUES (6, 'Pinwheel', 'This one goes round and round and doesn't stop', true, true, 86, 664, 75, 6);
INSERT INTO public.galaxy VALUES (7, 'Comet', 'Might be Halleys or not', true, false, 976, 45, 9, 7);
INSERT INTO public.galaxy VALUES (8, 'Sombreo galaxy', 'This looks like a sombreo or a hat from the south', true, true, 77, 32, 6, 8);


--
-- Data for Name: meteor; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.meteor VALUES (1, 'Halley Comet the one everyone wants to see', 'This is a famous one and well known', false, false, 96, 25, 32, 3);
INSERT INTO public.meteor VALUES (2, 'Big dipper not the little one', 'This is another famous one and well renown', true, true, 353, 49, 4, 32);
INSERT INTO public.meteor VALUES (3, 'Little Dipper not the big one', 'The small one but don't sleep on it or take it for granted', true, false, 45, 74, 324, 3);
INSERT INTO public.meteor VALUES (4, 'Aqua or the blue one', 'This is shaped like a man not anything else', true, true, 65, 56, 78, 5);

--
-- Data for Name: moon; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.moon VALUES (1, 'Moon', 'Everyone knows this one, you know the big dawg', true, false, 483, 83, 44, 3);
INSERT INTO public.moon VALUES (2, 'Europa', 'This is a famous one I think', true, true, 505, 98, 2, 4);
INSERT INTO public.moon VALUES (3, 'Ganymede', 'This one is out there and not close', false, false, 53, 925, 9, 2);
INSERT INTO public.moon VALUES (4, 'Io', 'This is a new one and never heard of', true, true, 923, 872, 3, 4);
INSERT INTO public.moon VALUES (5, 'Mimas', 'Another new one or maybe', true, true, 7523, 943, 8, 53);
INSERT INTO public.moon VALUES (6, 'Thebe', 'This is far too', true, false, 24, 50, 32, 8);
INSERT INTO public.moon VALUES (7, 'Amalthea', 'This is so pretty', true, false, 8, 83, 236, 4);
INSERT INTO public.moon VALUES (8, 'Carme', 'This is alot to take in', false, true, 8308, 7466, 85, 8);
INSERT INTO public.moon VALUES (9, 'Himilia', 'This is a big one', false, false, 554, 483, 8, 9);
INSERT INTO public.moon VALUES (10, 'Dione', 'Pretty name with good colors', false, true, 93, 445, 36, 101);
INSERT INTO public.moon VALUES (11, 'Ainite', 'It is out there and not coming in', false, false, 844, 54, 29, 13);
INSERT INTO public.moon VALUES (12, 'Elara', 'Another pretty name you already know', false, true, 94, 853, 22, 15);
INSERT INTO public.moon VALUES (13, 'Harry', 'From the potter or maybe not from the potter', true, false, 35, 4837, 882, 14);
INSERT INTO public.moon VALUES (14, 'Hermippe', 'This is out there too and no where close', false, false, 992, 450, 66, 4);
INSERT INTO public.moon VALUES (15, 'Aoede', 'This is a new one too and never had heard of', false, false, 24, 548, 5, 25);
INSERT INTO public.moon VALUES (16, 'Heike', 'This is spaced out and out throught there', true, true, 955, 90, 35, 11);
INSERT INTO public.moon VALUES (17, 'Carpo', 'This out there with you or someone else who knows', false, true, 983, 6, 3, 19);
INSERT INTO public.moon VALUES (18, 'Kalyke', 'This one gets around', true, false, 47, 37, 7, 20);
INSERT INTO public.moon VALUES (19, 'Tethys', 'Looks interesting', true, true, 92, 597, 20, 18);
INSERT INTO public.moon VALUES (20, 'Herse', 'This one maybe one of those ones', false, false, 757, 165, 18, 35);
INSERT INTO public.moon VALUES (24, 'Cyliene', 'This one is red and a very bright red and did I say bright', false, true, 195, 235, 94, 25);
INSERT INTO public.moon VALUES (25, 'Eirene', 'This one looks as if it could be split between two or maybe even three', true, ture, 119, 14, 49, 25);
INSERT INTO public.moon VALUES (26, 'Eukelade', 'One that is not full', true, false, 97, 46, 453, 25);
INSERT INTO public.moon VALUES (27, 'Titan', 'This is a gargatuan one', false, true, 72, 308, 83, 24);
INSERT INTO public.moon VALUES (32, 'Harpo', 'I have been fighting all my life head ass rofl', false, false, 3847, 549, 3, 32);
INSERT INTO public.moon VALUES (33, 'Sinope', 'Another empty space', true, true, 25, 24, 3, 36);
INSERT INTO public.moon VALUES (34, 'Megacite', 'Not that mega at all more like reggie', false, ture, 58, 23, 8, 20);
INSERT INTO public.moon VALUES (35, 'Charon', 'Very pretty and outstanding', true, ture, 855, 44, 173, 33);

--
-- Data for Name: planet; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.planet VALUES (1, 'Jupiter', 'One of those ones you alreday know', true, true, 93, 28, 42, 1);
INSERT INTO public.planet VALUES (2, 'Saturn', 'The big dawg and old too that father energy', false, true, 85, 985, 3, 7);
INSERT INTO public.planet VALUES (3, 'Venus', 'Bring me those fortunes and may they never stop', true, true, 23, 91, 8, 3);
INSERT INTO public.planet VALUES (4, 'Pluto', 'The little dawg and still a planet in my eyes', false, true, 55, 624, 72, 4);
INSERT INTO public.planet VALUES (5, 'Mars', 'The warlord always strapped and ready', true, false, 822, 77, 91, 7);
INSERT INTO public.planet VALUES (6, 'Mercury', 'Not the maurder but the real one', true, false, 825, 98, 9, 4);
INSERT INTO public.planet VALUES (7, 'Neptune', 'The lovely one and maybe fair', false, false, 35, 78, 96, 7);
INSERT INTO public.planet VALUES (8, 'Earth', 'The famous one and one we are on', false, true, 3, 86, 5, 8);
INSERT INTO public.planet VALUES (9, 'Uranus', 'The interesitng one and maybe the most verstaile', true, true, 653, 503, 63, 7);
INSERT INTO public.planet VALUES (10, 'Harry', 'Made up one and not real', false, true, 64, 335, 35, 10);
INSERT INTO public.planet VALUES (11, 'Ceres', 'The tempting and alluring one', true, false, 71, 37, 2, 17);
INSERT INTO public.planet VALUES (12, 'Charon', 'Might be a moon or maybe even galaxy', false, false, 85, 61, 2, 19);

--
-- Data for Name: star; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.star VALUES (1, 'Betelguse', 'Not the movie but the real thing', true, false, 87, 23, 3, 7);
INSERT INTO public.star VALUES (2, 'Rigel', 'Bright and very pretty', false, true, 64, 78, 723, 5);
INSERT INTO public.star VALUES (3, 'Sirius', 'The one and only', true, true, 67, 23, 32, 5);
INSERT INTO public.star VALUES (4, 'Pollux', 'Very pretty and fair', true, false, 622, 46, 9, 6);
INSERT INTO public.star VALUES (5, 'Deneb', 'Might be fake or this might be the real onw', true, false, 65, 23, 69, 3);
INSERT INTO public.star VALUES (6, 'Antares', 'The mighty and organe one', false,true, 875, 39, 8, 8);
INSERT INTO public.star VALUES (7, 'Vega', 'The famous one and well known one', false, true, 421, 65, 38, 7);

--
-- Name: galaxy_foreign_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_foreign_id_seq', 40, true);


--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_galaxy_id_seq', 40, true);


--
-- Name: meteor_foreign_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.meteor_foreign_id_seq', 4, true);


--
-- Name: meteor_meteor_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.meteor_meteor_id_seq', 4, true);


--
-- Name: moon_foreign_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.moon_foreign_id_seq', 60, true);


--
-- Name: moon_moon_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.moon_moon_id_seq', 60, true);


--
-- Name: planet_foreign_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.planet_foreign_id_seq', 12, true);


--
-- Name: planet_planet_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.planet_planet_id_seq', 12, true);


--
-- Name: star_foreign_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.star_foreign_id_seq', 8, true);


--
-- Name: star_star_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.star_star_id_seq', 8, true);

--
-- Name: galaxy galaxy_age_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_age_key UNIQUE (age);


--
-- Name: galaxy galaxy_f_id_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_f_id_key UNIQUE (f_id);


--
-- Name: galaxy galaxy_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_pkey PRIMARY KEY (galaxy_id);
    
--
-- Name: meteor meteor_age_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.meteor
    ADD CONSTRAINT meteor_age_key UNIQUE (age);


--
-- Name: meteor meteor_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.meteor
    ADD CONSTRAINT meteor_pkey PRIMARY KEY (meteor_id);


--
-- Name: moon moon_age_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_age_key UNIQUE (age);
