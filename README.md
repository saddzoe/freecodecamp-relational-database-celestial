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
